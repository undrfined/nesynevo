<script lang="ts">
    import iconPill from "$lib/assets/pill.svg";
    import iconHospital from "$lib/assets/hospital.svg";
    import iconMicroscope from "$lib/assets/microscope.svg";

    const icons = { pill: iconPill, hospital: iconHospital, microscope: iconMicroscope };

    export let name: string;
    export let icon: keyof typeof icons;

</script>

<div class="card" on:click={() => {
    location.href = "/clinic";
}}>
    <div class="header">
        <div class="header-icon">
            <img src={icons[icon]} class="icon">
        </div>
        <span class="header-text">{name}</span>
    </div>

    <div class="btn">
        <img src={iconHospital} class="icon">
        <span>0 clinics available</span>
    </div>
</div>

<style lang="scss">
    .card {
        background: #FFFFFF;
        border-radius: 16px;

        display: flex;
        flex-direction: column;
    }

    .header {
        margin: 16px 10px;
        display: flex;
        flex-direction: column;
        gap: 12px;

        min-height: 108px;
    }

    .header-icon {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        border: 2px solid #F1F1F3;
        display: flex;
        align-items: center;
        justify-content: center;

        .icon {
            width: 16px;
            height: 16px;
        }
    }

    .header-text {
        font-size: 16px;
        line-height: 28px;
        font-weight: 600;
    }

    .btn {
        border-radius: 14px;
        margin: 2px;
        display: flex;
        flex-direction: row;
        align-items: center;
        padding: 12px 8px;
        gap: 4px;
        background: #F7F7F8;
        color: #121212;

      .icon {
        width: 16px;
        height: 16px;
      }
    }


</style>
