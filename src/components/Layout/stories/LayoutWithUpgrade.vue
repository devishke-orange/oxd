<!--
/*
 * This file is part of OrangeHRM Inc
 *
 * Copyright (C) 2020 onwards OrangeHRM Inc
 *
 * This program is free software; you can redistribute it and/or modify
 * it under the terms of the GNU General Public License as published by
 * the Free Software Foundation; either version 3 of the License, or
 * (at your option) any later version.
 *
 * This program is distributed in the hope that it will be useful,
 * but WITHOUT ANY WARRANTY; without even the implied warranty of
 * MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 * GNU General Public License for more details.
 *
 * You should have received a copy of the GNU General Public License
 * along with this program.  If not, see  http://www.gnu.org/licenses
 */
-->

<template>
  <oxd-layout
    :user="user"
    context-title="Personal Information Manager"
    :sidepanel-menu-items="sidepanelMenuItems"
    :topbar-menu-items="topbarMenuItems"
    :brand-logo-src="brandLogoSrc"
    :brand-banner-src="brandBannerSrc"
    :breadcrumb="breadcrumb"
    :show-upgrade="true"
    upgrade-label="Upgrade"
    upgrade-url="https://orangehrm.com"
  >
    <p class="context-default">slot for context</p>
    <template #user-actions>
      <li role="none">
        <a href="#" role="menuitem" class="oxd-userdropdown-link"> Logout </a>
      </li>
    </template>
    <template #nav-actions>
      <oxd-icon-button name="question-lg" />
    </template>
    <template #footer>
      <p class="context-footer">slot for footer</p>
      <br />
    </template>
  </oxd-layout>
</template>

<script>
import {topMenuItems, sidePanelItems, breadcrumb} from './mockdata';
import Layout from '@/components/Layout/Layout.vue';
import IconButton from '@/components/Button/Icon.vue';

export default {
  name: 'LayoutWithUpgrade',

  components: {
    'oxd-layout': Layout,
    'oxd-icon-button': IconButton,
  },

  data() {
    return {
      brandLogoSrc: '/images/orange.png',
      brandBannerSrc: '/images/orangehrm-logo.png',
      user: {
        firstName: 'Jeff',
        lastName: 'Winger',
        profImgSrc: '/images/user-default-400.png',
      },
      sidepanelMenuItems: sidePanelItems,
      topbarMenuItems: topMenuItems,
      breadcrumb: breadcrumb,
    };
  },
};
</script>

<style scoped>
.context-default {
  background-color: rgba(255, 0, 0, 0.37);
  text-align: center;
  padding: 25% 0;
}
.context-footer {
  background-color: rgb(160 210 249);
  text-align: center;
  margin: 0 3rem;
}
</style>
