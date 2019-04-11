<template>
  <div class="treeNodeWrapper">
    <ul class="treeNodeUl">
      <li class="treeNodeLi">
        <span><input type="checkbox" :checked="isChecked"/></span>
        <i :class="['icon', 'fa', config.glyph]" aria-hidden="true"></i>
        <a href='#' v-on:click="onToggle" :class="textClass">{{config.text}}</a>
      </li>
      <TreeNode
        v-if="isExpanded"
        v-for="treeNode in config.children"
        :config="treeNode"
        :key="treeNode.text"
      />
    </ul>
  </div>
</template>

<script lang="js">
export default  {
  name: "TreeNode",
  props: {
    config: Object
  },
  data () {
    return {
      isExpanded: (typeof this.config.expanded === 'boolean'? this.config.expanded: false),
      isChecked: (typeof this.config.checked === 'boolean'? this.config.checked: false)
    }
  },
  computed: {
    textClass: function() {
      let textClass = 'config.leaf';
      switch(true) {
        case this.config.leaf:
          textClass = 'leaf';
          break;
        case this.isExpanded:
          textClass = 'nodeExpanded';
          break;
        case !this.isExpanded:
          textClass = 'nodeCollapsed';
          break;
      }
      return textClass;
    }
  },
  methods: {
    onToggle: function() {
      if(this.config.leaf) {
        this.isChecked = !this.isChecked;
      } else {
        this.isExpanded = !this.isExpanded;
      }
    }
  }
}
</script>
<style scoped>
  .treeNodeWrapper {
    text-align: left;
    padding-left: 5px;
    vertical-align: middle;
  }

  .treeNodeUl {
    padding-left: 10px;
    margin: 5px;
  }

  .treeNodeLi {
    list-style-type: none;
    padding-left: 5px;
    margin-left: 5px;
  }

  a:link,
  a:visited,
  a:hover,
  a:active {
    text-decoration: none;
    color: inherit;
  }

  .leaf {
    font-weight: normal;
  }

  .icon {
    color: #5f6368;
    margin-right: 10px;
    margin-left: 5px;
  }
  .nodeExpanded,
  .nodeCollapsed {
    font-weight: bold;
  }

</style>
