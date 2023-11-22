<script lang="ts">
    import editIcon from "$lib/assets/edit.svg";
    import geoIconFilled from "$lib/assets/geo-fill.svg";
    import Card from "$lib/common/Card.svelte";
</script>

<svelte:head>
    <title>User</title>
    <meta name="description" content="User" />
</svelte:head>

<div class="profile-header">
    <div class="profile-name">
        Lili Kende
        <img src={editIcon} alt="" class="icon">
    </div>
    <div class="profile-info">
        <span>+1 610 245 8324</span>
        <span>•</span>
        <span class="profile-info-location"><img class="icon" src={geoIconFilled} alt="">New York, USA</span>
    </div>
    <div class="profile-header-inner">
        <div class="param">
            <div class="value">Female</div>
            <div class="name">Sex</div>
        </div>
        <div class="param">
            <div class="value">II</div>
            <div class="name">RH+</div>
        </div>
        <div class="param">
            <div class="value">24</div>
            <div class="name">Age</div>
        </div>
    </div>
</div>



<style lang="scss">
    .profile-name {
        display: flex;
        align-items: center;
        font-size: 24px;
        font-weight: 500;
        line-height: 40px;
        color: #000000;
      gap: 8px;

      .icon {
        width: 16px;
        height: 16px;
      }
    }

    .profile-info {
        display: flex;
        color: #A8ACB8;
        gap: 16px;
      justify-content: center;
    }

    .profile-info-location {
        display: flex;
        align-items: center;
        gap: 2px;

        .icon {
            width: 16px;
            height: 16px;
        }
    }

    .profile-header {
        overflow: hidden;
        border-radius: 20px;
        background: #FFFFFF;
        padding-top: 16px;
        display: flex;
        flex-direction: column;
        justify-content: center;
      align-items: center;
        gap: 12px;
        margin: 0 20px;
      margin-top: 56px;
    }

    .profile-header-inner {
        margin-top: 12px;
        background: #F7F7F8;
        border-top-left-radius: 16px;
        border-top-right-radius: 16px;
        display: flex;
        padding: 16px 20px;
        width: 100%;
        justify-content: space-between;
        align-items: center;

      .param {
        display: flex;
        flex-direction: column;
        gap: 16px;
        .value {
          color: #000000;
        }
        .name {
          color: #A8ACB8;
        }
      }
    }
</style>
