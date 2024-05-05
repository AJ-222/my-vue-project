<template>

  <div class="admin-panel">
    <div class="tabs" ref="tabsContainer">
      <div class="tab" v-for="(tab, index) in tabs" :key="index" @click="activeTab = index" :class="{ active: activeTab === index }">
        {{ tab.title }}
      </div>
    </div>
    <div class="tab-content">
      <div v-if="activeTab === 0">
        <h2>Manage Users</h2>
        <textarea v-model="juser" rows="30" cols="50"></textarea>

       
      </div>
      <div v-else-if="activeTab === 1">
        <h2>Manage Existing Funds</h2>
        <!-- Your manage existing funds content goes here -->
         <textarea v-model="jsonDataString" rows="30" cols="50"></textarea>
      </div>
      <div v-else>
        <h2>Fund Manager requests</h2>
         <textarea v-model="jreq" rows="30" cols="50"></textarea>
      </div>
    </div>
  </div>
</template>

<script>
import jsonData from '../fundmandata.json';
import userData from '../userdata.json';
import reqData from '../req.json';
export default {
  data() {
    return {
      activeTab: 0,
      tabs: [
        { title: "Manage Users" },
        { title: "Manage Existing Funds" },
        { title: "Fund Manager requests" }
      ],
      jsonDataString: JSON.stringify(jsonData, null, 2),
     juser: JSON.stringify(userData, null, 2),
       jreq: JSON.stringify(reqData, null, 2)
    };
  },
  mounted() {
    this.setupScrolling();
  },
  methods: {
    setupScrolling() {
      const tabsContainer = this.$refs.tabsContainer;
      if (tabsContainer) {
        tabsContainer.style.display = 'flex';
        tabsContainer.style.overflowX = 'auto';
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.admin-panel {
  display: flex;
  flex-direction: column;
}

.tabs {
  white-space: nowrap; /* Ensures tabs don't wrap */
}

.tab {
  cursor: pointer;
  padding: 10px;
  margin-bottom: 5px;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  display: inline-block; /* Display tabs inline */
}

.tab.active {
  background-color: #fff;
  font-weight: bold;
}

.tab-content {
  margin-top: 10px; /* Add some spacing */
}

.tab-content h2 {
  margin-top: 0;
}
</style>

<!--jsonDataString: JSON.stringify(jsonData, null, 2) // Convert JSON data to string-->
