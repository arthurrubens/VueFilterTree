<template>
  <div class="filterTreeWrapper">
    <div class="filterTreeTitle">
      <span>{{title}}</span>
    </div>
    <input type="text" class="filterInput" v-model="filterText" placeholder="Filter by..."/>
    <TreeNode
      class="treeNode"
      v-for="treeNodeData in clonedData"
        :config="treeNodeData"
      :key="treeNodeData.text"
    />
  </div>
</template>

<script lang="js">
import TreeNode from '@/components/TreeNode.vue';

export default  {
  name: "FilterTree",
  components: {
    TreeNode
  },
  props: {
    title: String,
    data: Array
  },

  data: function() {
    return {
      filterText: '',
      clonedData: JSON.parse(JSON.stringify(this.data))
    }
  },
  watch: {
    filterText: function(filterText) {
      function filterData(data, property, filterText, anyMatch) {
          var r = data.filter(function (item) {
              if (item.children) {
                  item.children = filterData(item.children, property, filterText, anyMatch);
                  return item.children.length > 0;
              };
              if(anyMatch) {
                  return item[property].toLocaleLowerCase().indexOf(filterText) > -1;
              } else {
                  return item[property].toLocaleLowerCase().startsWith(filterText);
              }
          });
          return r;
      }
      this.clonedData = filterData(JSON.parse(JSON.stringify(this.data)), 'text', filterText.toLowerCase(), true);
    }
  }
}
</script>
<style scoped>
  .filterTreeWrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: #f5f5f5;
    border: 1px solid #dcdfe2;
    width: 400px;
    border-radius: 5px;
    margin: 60px auto 0 auto;
  }
  .filterTreeTitle {
    font-family: "Helvetica Neue",Arial,sans-serif;
    border-bottom: 1px solid #cdcdcd;
    font-size: 20px;
    line-height: 1.5;
    color: #3a434f;
    width: 100%;
  }
  .filterInput {
    font-size: 16px;
    width: calc(100% - 20px);
    left: 10px;
    right: 10px;
    margin-bottom: 10px;
    margin-top: 10px;
  }

  .treeNode{
    width: 90%;
    padding: 0px;
    margin: 0px;
  }
</style>