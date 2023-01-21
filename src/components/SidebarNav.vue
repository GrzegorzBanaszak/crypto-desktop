<script setup lang="ts">
import SidebarLink from "./SidebarLink.vue";
import OverviewIcon from "../icons/OverviewIcon.vue";
import BankIcon from "../icons/BankIcon.vue";
import WalletsIcon from "../icons/WalletsIcon.vue";
import BundlesIcon from "../icons/BundlesIcon.vue";
import ReportingIcon from "../icons/ReportingIcon.vue";
import CommunityIcon from "../icons/CommunityIcon.vue";
</script>

<template>
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
</template>

<style lang="scss">
.sidebar {
  &-nav {
    list-style-type: none;
    margin-top: 4rem;
  }
}
</style>
