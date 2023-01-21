<script setup lang="ts">
import LogoIcon from "../icons/LogoIcon.vue";
import SidebarLink from "./SidebarLink.vue";
import OverviewIcon from "../icons/OverviewIcon.vue";
import BankIcon from "../icons/BankIcon.vue";
import WalletsIcon from "../icons/WalletsIcon.vue";
import BundlesIcon from "../icons/BundlesIcon.vue";
import ReportingIcon from "../icons/ReportingIcon.vue";
import CommunityIcon from "../icons/CommunityIcon.vue";
</script>

<template>
  <aside className="sidebar-container">
    <h1 className="sidebar-logo"><LogoIcon /> Payte</h1>
    <ul className="sidebar-nav">
      <li>
        <sidebar-link
          :link-target="'/overview'"
          :link-text="'Overview'"
          :notification="9"
        >
          <OverviewIcon
        /></sidebar-link>
      </li>
      <li>
        <sidebar-link :link-target="'/buy-sell'" :link-text="'Buy / Sell'">
          <BankIcon
        /></sidebar-link>
      </li>
      <li>
        <sidebar-link :link-target="'/wallets'" :link-text="'Wallets'">
          <WalletsIcon
        /></sidebar-link>
      </li>
      <li>
        <sidebar-link :link-target="'/bundles'" :link-text="'Bundles'">
          <BundlesIcon
        /></sidebar-link>
      </li>
      <li>
        <sidebar-link :link-target="'/reporting'" :link-text="'Reporting'">
          <ReportingIcon
        /></sidebar-link>
      </li>
      <li>
        <sidebar-link :link-target="'/community'" :link-text="'Community'">
          <CommunityIcon
        /></sidebar-link>
      </li>
    </ul>
  </aside>
</template>

<style lang="scss">
.sidebar {
  &-container {
    background-color: #f7f7f9;
    width: 15%;
    padding: 1rem;
  }

  &-logo {
    display: flex;
    align-items: center;
    font-weight: 600;
    gap: 0.7rem;
  }
  &-nav {
    list-style-type: none;
    margin-top: 4rem;
  }
}
</style>
