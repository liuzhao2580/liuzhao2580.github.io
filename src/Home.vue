<template>
    <div class="Home-box">
        <router-view />
        <div class="bottomNav">
            <ul class="bottomNav-box">
                <li v-for="item in bottomNavData" :key="item.name" class="bottomNav-li">
                    <router-link :to="item.path">
                        <div class="imgBox">
                            <i :class="item.icon"></i>
                        </div>
                        <span>{{item.name}}</span>
                    </router-link>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "Home",
    components: {},
    props: {},
    data() {
        return {
            bottomNavData: [
                {
                    icon: "iconfont icon-shouye",
                    name: "首页",
                    path: "/home"
                },
                {
                    icon: "iconfont icon-shangpin",
                    name: "商品",
                    path: "/shop"
                },
                {
                    icon: "iconfont icon-gouwuche",
                    name: "购物车",
                    path: "/shopcar"
                },
                {
                    icon: "iconfont icon-yonghu",
                    name: "我的",
                    path: "/mine"
                }
            ]
        };
    },
    created() {},
    mounted() {},
    methods: {},
    watch: {}
};
</script>

<style lang="scss" scoped>
@import "@/assets/css/base.scss";
.Home-box {
    .bottomNav {
        position: absolute;
        bottom: 0;
        width: 100%;
        text-align: center;
        .bottomNav-box {
            display: flex;
            .bottomNav-li {
                width: 25%;
                .imgBox {
                    height: 70px;
                    i {
                        font-size: 50px;
                    }
                }
                .active {
                    color: $Color_red;
                }
            }
        }
    }
}
</style>
