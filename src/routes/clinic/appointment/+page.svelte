<script>
    // You would add your script here for handling state, such as selected date and time
</script>

<style>
    .container {
        background: white;
        max-width: 375px;
        margin: auto;
        font-family: 'Arial', sans-serif;
        color: #333;
        border-radius: 20px;
        overflow: hidden;
    }

    .clinic-header {
        padding: 20px;
        text-align: center;
        border-bottom: 1px solid #ccc;
    }

    .clinic-title {
        font-size: 20px;
        margin: 0;
        font-weight: normal;
    }

    .clinic-address {
        font-size: 14px;
        color: #666;
    }

    .appointment-header {
        font-size: 24px;
        text-align: center;
        padding: 20px;
    }

    .date-time-container {
        padding: 0 20px 20px;
    }

    .date-time-title {
        font-size: 18px;
        margin: 20px 0;
    }

    .date-time-slots {
        display: flex;
        overflow-x: auto;
        margin-bottom: 20px;
    }

    .date-time-slot {
        min-width: 60px;
        padding: 10px;
        margin-right: 10px;
        background: #f0f0f0;
        border-radius: 10px;
        text-align: center;
    }

    .time-slots {
        display: flex;
        justify-content: space-between;
    }

    .time-slot {
        padding: 10px;
        background: #f0f0f0;
        border-radius: 10px;
        flex: 1;
        margin-right: 10px;
    }

    .time-slot:last-child {
        margin-right: 0;
    }

    .note {
        padding: 20px;
        background: #f0f0f0;
        font-size: 14px;
        color: #666;
        text-align: center;
    }

    .confirm-button {
        background: black;
        color: white;
        border: none;
        width: calc(100% - 40px);
        padding: 15px;
        margin: 20px;
        font-size: 16px;
        border-radius: 20px;
    }

    /* Add styles for the SVG icons */
</style>

<div class="container">
    <div class="clinic-header">
        <h1 class="clinic-title">VitalityCare Clinic</h1>
        <p class="clinic-address">2972 Westheimer Rd. Santa Ana, Illinois 85486</p>
        <!-- SVG for the star rating will go here -->
    </div>

    <div class="appointment-header">
        Select date and time of your appointment
    </div>

    <div class="date-time-container">
        <div class="date-time-title">Available date & time</div>
        <div class="date-time-slots">
            <!-- Repeat for each date -->
            <div class="date-time-slot">MON 25 MAY</div>
            <!-- ... -->
        </div>

        <div class="time-slots">
            <!-- Repeat for each time -->
            <div class="time-slot">8 AM</div>
            <!-- ... -->
        </div>
    </div>

    <div class="note">
        Please note that blood checks are only available on an empty stomach, so if you prefer to proceed with blood donation only, please cancel your check before your appointment.
    </div>

    <button class="confirm-button">Confirm & Next</button>
</div>

