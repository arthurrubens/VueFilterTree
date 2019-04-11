<template>
  <div id="app">
    <FilterTree
      title="Filter Tree"
      :data="data"
    />
  </div>
</template>

<script>
import FilterTree from '@/components/FilterTree.vue'
import TreeNode from '@/components/TreeNode.vue'

export default {
  name: "App",
  components: {
    FilterTree,
    TreeNode
  },
  data: function() {
    return {
      data: [{
        text: "Mac",
        id: "Mac",
        glyph: 'fa-laptop',
        children: [{
            text: "Macbook",
            id: "Mac-Macbook",
            glyph: 'fa-laptop',
            leaf: true
        }, {
            text: "Macbook Air",
            id: "Mac Macbook Air",
            glyph: 'fa-laptop',
            children: [{
                text: "Macbook Air 13-inch",
                id: "Mac-MacbookAir-13-inch",
                glyph: 'fa-laptop',
                leaf: true
            }, {
                text: "Macbook Air 15-inch",
                id: "Mac-MacbookAir-15-inch",
                glyph: 'fa-laptop',
                leaf: true
            }]
        }, {
            text: "Macbook Pro",
            id: "Mac-MacbookPro",
            glyph: 'fa-laptop',
            children: [{
                text: "Macbook Pro 13-inch",
                id: "Mac-MacbookPro-13-Inch",
                glyph: 'fa-laptop',
                leaf: true
            }, {
                text: "Macbook Pro 15-inch",
                id: "Mac-MacbookPro-15-Inch",
                glyph: 'fa-laptop',
                leaf: true
            }]
        }, {
            text: "iMac",
            id: "Mac-iMac",
            glyph: 'fa-desktop',
            children: [{
                text: "iMac 21.5-inch",
                id: "Mac-iMac-21.5-Inch",
                glyph: 'fa-desktop',
                leaf: true
            }, {
                text: "iMac 27-inch",
                id: "Mac-iMac-27-Inch",
                glyph: 'fa-desktop',
                leaf: true
            }, {
                text: "iMac Pro",
                id: "Mac-iMacPro",
                glyph: 'fa-desktop',
                leaf: true
            }]
        }, {
            text: "Mac Pro",
            id: "Mac-MacPro",
            glyph: 'fa-laptop',
            leaf: true
        }, {
            text: "Mac mini",
            id: "Mac-MacMini",
            glyph: 'fa-laptop',
            leaf: true
        }]
    }, {
        text: "iPad",
        id: "iPad",
        glyph: 'fa-tablet',
        children: [{
            text: "12.9-in. iPad Pro",
            id: "iPad-12.9-Inch",
            glyph: 'fa-tablet',
            leaf: true
        }, {
            text: "10.5-in. iPad Pro",
            id: "iPad-iPad-10.5-Inch",
            glyph: 'fa-tablet',
            leaf: true
        }, {
            text: "iPad",
            id: "iPad-iPad",
            glyph: 'fa-tablet',
            leaf: true
        }, {
            text: "iPad mini 4",
            id: "iPad-iPad-Mini-4",
            glyph: 'fa-tablet',
            leaf: true
        }, {
            text: "12.9-in. iPad Pro",
            id: "iPad-iPad-12.9-Inch",
            glyph: 'fa-tablet',
            leaf: true
        }]
    }, {
        text: "iPhone",
        id: "iPhone",
        glyph: 'fa-mobile',
        children: [{
            text: "iPhone X",
            id: "iPhone-iPhone-X",
            glyph: 'fa-mobile',
            leaf: true
        }, {
            text: "iPhone 8 Plus",
            id: "iPhone-iPhone-8-Plus",
            glyph: 'fa-mobile',
            leaf: true
        }, {
            text: "iPhone 8",
            id: "iPhone-iPhone-8",
            glyph: 'fa-mobile',
            leaf: true
        }, {
            text: "iPhone 7 Plus",
            id: "iPhone-iPhone-7-Plus",
            glyph: 'fa-mobile',
            leaf: true
        }, {
            text: "iPhone 6S Plus",
            id: "iPhone-iPhone-6S-Plus",
            glyph: 'fa-mobile',
            leaf: true
        }, {
            text: "iPhone 6S",
            id: "iPhone-iPhone-6S",
            glyph: 'fa-mobile',
            leaf: true
        }, {
            text: "iPhone SE",
            id: "iPhone-iPhone-SE",
            glyph: 'fa-mobile',
            leaf: true
        }]
    }, {
        text: "Watch",
        id: "Watch",
        glyph: 'fa-clock-o',
        children: [{
            text: "Watch Series 3 GPS + Cellular",
            id: "Watch-Watch-Series-3-GPS-Cellular",
            glyph: 'fa-clock-o',
            leaf: true
        }, {
            text: "Watch Series 3 GPS",
            id: "Watch-Watch-Series-3-GPS",
            glyph: 'fa-clock-o',
            leaf: true
        }, {
            text: "Watch Series 1",
            id: "Watch-Watch-Series-1",
            glyph: 'fa-clock-o',
            leaf: true
        }, {
            text: "Apple Watch Hermès",
            id: "Watch-Watch-Hermes",
            glyph: 'fa-clock-o',
            leaf: true
        }, {
            text: "Apple Watch Edition",
            id: "Watch-Watch-Edition",
            glyph: 'fa-clock-o',
            leaf: true
        }]
    }, {
        text: "TV",
        id: "TV",
        glyph: 'fa-television',
        children: [{
            text: "Apple TV 4K",
            id: "TV-4K",
            glyph: 'fa-television',
            leaf: true
        }, {
            text: "Apple TV",
            id: "TV-TV",
            glyph: 'fa-television',
            leaf: true
        }]
    }, {
        text: "HomePod",
        id: "HomePod",
        glyph: 'fa-gift',
        leaf: true
    }, {
        text: "iPod touch",
        id: "iPod-Touch",
        glyph: 'fa-mobile',
        leaf: true
    }, {
        text: "AirPods",
        id: "AirPods",
        glyph: 'fa-headphones',
        leaf: true
    }]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>
