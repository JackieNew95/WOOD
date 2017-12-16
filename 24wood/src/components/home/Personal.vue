<template>
    <div class="personal">
        <header>
            <div class="hmain">
                <div class="hleft">
                    <div>登录</div>
                    <div>注册</div>
                </div>
                <div class="hright">
                    <router-link :to="{name:'personal'}"><img src="../../assets/img/wo.png" alt=""></router-link>
                    <router-link :to="{name:'personal'}"><img src="../../assets/img/gouwu.png" alt=""></router-link>
                </div>
            </div>
        </header>
        <nav>

        </nav>
        <div class="ts">
            <div class="tmain">
                <a href="">首页</a>
                <span>&gt;&gt;</span>
                <a href="">个人中心</a>
            </div>
        </div>
        <div class="pmain">
            <div class="pleft">
                <div class="pl-top">
                    <img src="../../assets/img/y.jpg" alt="">
                    <span>丸子君</span>
                </div>
                <div class="pl-bot">
                    <div class="plb-top">
                        <img src="../../assets/img/mtou.jpg" alt="">
                        <span>交易管理|JIAOYIGUANLI</span>
                    </div>
                    <ul class="plb-center">
                        <img src="../../assets/img/order.png" alt="">
                        <h4>我|的|订|单</h4>
                        <li class="allorder">全部订单</li>
                        <li class="sucorder">成功订单</li>
                        <li class="canorder">取消订单</li>
                    </ul>
                    <div class="plb-bot">
                        <img src="../../assets/img/order.png" alt="">
                        <h4>我|的|评|论</h4>
                    </div>
                </div>
            </div>
            <div class="pright">
                <div class="pright-top">
                    <img src="../../assets/img/mutou2.jpg" alt="">
                    <ul class="prt-main">
                        <li>商品图片</li>
                        <li>单价(元)</li>
                        <li>数量</li>
                        <li>小计(元)</li>
                        <li>订单状态</li>
                        <li>编辑</li>
                    </ul>
                </div>
                <ul class="pright-bot">
                    <ul>
                        <li>
                            <div class="prbot-img">
                                <img src="../../assets/img/tj1.png" alt="">
                                <span>ZAKKA实木圆盘</span>
                                <span>颜色/米色 英寸/5英寸</span>
                            </div>
                        </li>
                        <li>60.00</li>
                        <li>2</li>
                        <li>120.00</li>
                        <li>交易成功</li>
                        <li>
                            <div>追加评价</div>
                            <div>查看订单</div>
                        </li>
                    </ul>
                </ul>
            </div>
        </div>
        <div class="tj">
            <img src="../../assets/img/tui.png" alt="">
            <ul class="tuimain">
                <li>
                    <div class="zhe">
                        <div class="zhenei">
                            <span>分类（创意厨房用具）</span>
                            <div class="xian1">
                                <div class="xian2"></div>
                            </div>
                            <span>价格</span>
                        </div>
                    </div>
                    <img src="../../assets/img/tj1.png" alt="">
                    <span>名字</span>
                    <span>描述</span>
                </li>
                <li>
                    <div class="zhe">
                        <div class="zhenei">
                            <span>分类（创意厨房用具）</span>
                            <div class="xian1">
                                <div class="xian2"></div>
                            </div>
                            <span>价格</span>
                        </div>
                    </div>
                    <img src="../../assets/img/tj1.png" alt="">
                    <span>名字</span>
                    <span>描述</span>
                </li>
                <li>
                    <div class="zhe">
                        <div class="zhenei">
                            <span>分类（创意厨房用具）</span>
                            <div class="xian1">
                                <div class="xian2"></div>
                            </div>
                            <span>价格</span>
                        </div>
                    </div>
                    <img src="../../assets/img/tj1.png" alt="">
                    <span>名字</span>
                    <span>描述</span>
                </li>
            </ul>
            <ul class="tbtn">
                <span>&lt;</span>
                <li></li>
                <li></li>
                <li></li>
                <span>&gt;</span>
            </ul>
        </div>
    </div>
</template>
<script>
    export default {
        name:'personal'
    }
</script>
<style>
    @import "../../assets/css/personal.css";
</style>