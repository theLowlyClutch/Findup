<template>
<div>
  <b-navbar toggleable="lg" type="light" id="header">
    <b-navbar-brand href="#">FindUp</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="/" >{{ $t('header.home') }}</b-nav-item>
        <b-nav-item :to="`/${$i18n.locale}/about`">{{ $t('header.about') }}</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">

        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-5" placeholder="Search"></b-form-input>
        </b-nav-form>
     

       <b-navbar-nav class="ml-auto">
          

          
          <b-nav-item :to="`/${$i18n.locale}/login`">{{ $t('header.login') }}</b-nav-item>
          <b-nav-item :to="`/${$i18n.locale}/signup`">{{ $t('header.signup') }}</b-nav-item>
  
        </b-navbar-nav>
          
        <b-nav-item-dropdown text="Lang" right>
          <b-dropdown-item  @click="setLocale('en')">ENG</b-dropdown-item>
          <b-dropdown-item  @click="setLocale('et')">EST</b-dropdown-item>
        </b-nav-item-dropdown>

        <!--removed dropdown due to a technical issues -->
        <!-- <b-nav-item-dropdown right>
          <template #button-content>
            <em>User</em> 
          </template>
          <b-dropdown-item href=" ">Settings</b-dropdown-item> 
          <b-dropdown-item href=" ">Sign Out</b-dropdown-item> 
        </b-nav-item-dropdown> -->

        
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>

</template>

<script>
export default {
  name: 'Header',
  data () {
    return {

    }
  },
  methods: {
    setLocale(locale) {
      this.$i18n.locale = locale;
      this.$router.push(
        {
          params: {
            lang: locale,
          },
        },
        () => {}
      );
    },

  }
}
</script>

<style>
#header{
  background-color:cornflowerblue;
}

.dropdown-item:hover {
  background-color: green ;

}

</style>
