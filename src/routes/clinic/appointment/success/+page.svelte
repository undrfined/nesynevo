<script>
    function addToCalendar(title, description, location, startTime, endTime) {
        // Format dates as YYYYMMDDTHHmmssZ
        const startDate = formatDateTime(startTime);
        const endDate = formatDateTime(endTime);

        const icsFileContent = [
            'BEGIN:VCALENDAR',
            'VERSION:2.0',
            'BEGIN:VEVENT',
            `SUMMARY:${escapeICSValue(title)}`,
            `DESCRIPTION:${escapeICSValue(description)}`,
            `LOCATION:${escapeICSValue(location)}`,
            `DTSTART:${startDate}`,
            `DTEND:${endDate}`,
            'END:VEVENT',
            'END:VCALENDAR'
        ].join('\n');

        const blob = new Blob([icsFileContent], { type: 'text/calendar;charset=utf-8' });
        const link = document.createElement('a');
        link.href = URL.createObjectURL(blob);
        link.setAttribute('download', `${title}.ics`);
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
    }

    function formatDateTime(date) {
        // Converts Date object to ICS format: YYYYMMDDTHHmmssZ
        return date.toISOString().replace(/-|:|\.\d+/g, '');
    }

    function escapeICSValue(value) {
        // Escapes text as per ICS specification
        return value.replace(/\\/g, '\\\\').replace(/;/g, '\\;').replace(/,/g, '\\,').replace(/\n/g, '\\n');
    }

    // Example usage:

    // Function to schedule a reminder
    function scheduleReminder(title, text, dateTime) {
        // Ask for permission if notifications are not already granted
        if (Notification.permission !== 'granted') {
            Notification.requestPermission().then(permission => {
                if (permission === 'granted') {
                    createNotification(title, text, dateTime);
                }
            });
        } else {
            createNotification(title, text, dateTime);
        }
    }

    // Function to create a notification at the specific date and time
    function createNotification(title, text, dateTime) {
        const now = new Date().getTime();
        const targetTime = new Date(dateTime).getTime();
        const delay = targetTime - now;

        if (delay < 0) {
            console.error('The specified time is in the past. Please choose a future time.');
            return;
        }

        setTimeout(() => {
            new Notification(title, {
                body: text,
                // Optionally, you can add an icon, image, etc.
            });
        }, delay);
    }

    // Usage:
    // Replace 'Your Reminder Title', 'Your reminder text', and the date-time string with your desired values.



    // Include any necessary script logic for buttons

    function add() {
        let startTime = new Date();
        startTime.setSeconds(startTime.getSeconds() + 3);
        let endTime = new Date(startTime);
        endTime.setHours(endTime.getHours() + 1);
        addToCalendar(
            'Doctor Appointment',
            'Annual physical check-up',
            '123 Main St, Anytown, AN',
            startTime, // Start time
           endTime  // End time
        );
        // Logic to add to calendar
    }

    function sendReminder() {
        let startTime = new Date();
        startTime.setSeconds(startTime.getSeconds() + 3);
        scheduleReminder(
            'Doctor Appointment',
            'Annual physical check-up',
            startTime.toUTCString() // Make sure the date-time string is in the correct format
        );
        // Logic to send a reminder
    }
</script>

<style>
    .page-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 20px;
        height: 100vh;
        box-sizing: border-box;
        font-family: 'Arial', sans-serif;
        background: white;
    }

    .message {
        text-align: center;
        margin-bottom: 50px;
    }

    .message h1 {
        margin: 0;
        font-size: 24px;
        color: #333;
    }

    .message p {
        color: #666;
        font-size: 16px;
    }

    .button {
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 15px 30px;
        margin: 10px 0;
        border: 1px solid #ccc;
        border-radius: 10px;
        background: white;
        color: #333;
        font-size: 16px;
        cursor: pointer;
    }

    /* Placeholder for the icons next to the button text */
    .icon {
        margin-right: 10px;
        display: inline-block;
        width: 20px;
        height: 20px;
        background: url('$lib/assets/calendar.svg') no-repeat 50% 50%;

        &.remind {
            background: url('$lib/assets/notify-me.svg') no-repeat 50% 50%;
        }
    }
</style>

<div class="page-container">
    <div class="message">
        <h1>Thank You!</h1>
        <p>Thank you for being a part of our community. You will be notified within 24 hours of receiving the results of your blood check</p>
    </div>
    <button class="button" on:click={add}>
        <span class="icon"></span> Add To Calendar
    </button>
    <button class="button" on:click={sendReminder}>
        <span class="icon remind"></span> Send Me Reminder
    </button>
</div>
