<template>
  <div class="admin-panel">
    <div class="tabs">
      <div class="tab" v-for="(tab, index) in tabs" :key="index" @click="activeTab = index" :class="{ active: activeTab === index }">
        {{ tab.title }}
      </div>
    </div>
    <div class="tab-content">
      <div v-if="activeTab === 0">
        <h2>Manage Users</h2>
        <!-- Your manage users content goes here -->
      </div>
      <div v-else-if="activeTab === 1">
        <h2>Manage Existing Funds</h2>
        <!-- Your manage existing funds content goes here -->
      </div>
      <div v-else>
        <h2>Approve/Deny New Funds</h2>
        <!-- Your approve/deny new funds content goes here -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 0,
      tabs: [
        { title: "Manage Users" },
        { title: "Manage Existing Funds" },
        { title: "Approve/Deny New Funds" }
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.admin-panel {
  display: flex;
  flex-direction: row;
}

.tabs {
  display: flex;
  flex-direction: column;
}

.tab {
  cursor: pointer;
  padding: 10px;
  margin-bottom: 5px;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
}

.tab.active {
  background-color: #fff;
  font-weight: bold;
}

.tab-content {
  margin-left: 20px;
}

.tab-content h2 {
  margin-top: 0;
}
</style>
