<template>
    <div class="static">
        <div class="static-blog d-flex align-items-center justify-content-between ">
            <div class="item  d-flex align-items-start" v-for="( item , index) in blog" :key="index">
                <img :src="item.img" alt="">

                <div class="inform ">
                    <p class="inform-type">
                        {{ item.type }}
                    </p>

                    <p class="inform-amount">
                        {{ item.amount }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'Static',
    props:[
        "blog"
    ]
}
</script>

<style lang="scss">
.static{
    margin: 30px 0;
    &-blog{
        .item{
            background: white;
            box-shadow: 0px 12px 26px rgba(16, 30, 115, 0.06);
            border-radius: 8px;
            max-width: 250px;
            padding: 12px 12px 0 12px;
            width: 100%;

            &:hover{
                box-shadow: 5px 5px 5px rgba(255, 255, 255, 0.397);
            }

            .inform{
                margin: 0 22px;
                &-type{
                    font-weight: bold;
                    font-size: 14px;
                    line-height: 20px;
                    letter-spacing: 0.1px;
                    color: #25282B;
                }

                &-amount{
                    font-size: 18px;
                    line-height: 24px;
                    display: flex;
                    align-items: center;
                    letter-spacing: 0.1px;
                    color: #336CFB;
                }
            }
        }
    }
}
</style>