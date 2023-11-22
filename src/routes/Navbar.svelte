<script lang="ts">
    import iconPill from '$lib/assets/pill.svg';
    import iconPillFilled from '$lib/assets/pill-fill.svg';
    import iconHospital from '$lib/assets/hospital.svg';
    import iconHospitalFilled from '$lib/assets/hospital-fill.svg';
    import iconUser from '$lib/assets/user.svg';
    import iconUserFilled from '$lib/assets/user-fill.svg';
    import {page} from "$app/stores";
</script>

<div class="nav">
    <a href="/"><img src={$page.url.pathname === '/' ? iconPillFilled : iconPill} alt="" class="icon"></a>
    <a href="/hospitals"><img src={$page.url.pathname.startsWith('/hospitals') ? iconHospitalFilled : iconHospital} alt="" class="icon"></a>
    <a href="/user"><img src={$page.url.pathname.startsWith('/user') ? iconUserFilled : iconUser} alt="" class="icon"></a>
</div>

<style lang="scss">
    .nav {
      position: absolute;
      bottom: 0;
      width: 100%;
      background: #FFFFFF;
      display: flex;
      flex-direction: row;
      gap: 48px;
      padding: 12px 0;
      justify-content: center;
      align-items: center;
      border-top: 1px solid #F1F1F3;
    }

    .icon {
      width: 32px;
      height: 32px;
    }
</style>
