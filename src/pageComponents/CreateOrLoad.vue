<template>
  <div>
    <HeaderBar title="Setup" />
    <div class="options-box">
      <div class="body">
        <h1>Get Started</h1>
        <h2>Create a new vault, or open an existing vault</h2>

        <router-link
          class="btn"
          :to="{name: 'CreateStep1'}"
        >
          Create New Vault
        </router-link>

        <router-link
          class="btn"
          :to="{name: 'LoadChoose'}"
        >
          Open Existing Vault
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted(){
    try{
      this.$root.LoadLastUsedVault();
      this.$router.push({name: 'LoadUnlockStep1'});
    } catch (err){
      // do nothing if cache is empty
    }
  }
};
</script>
