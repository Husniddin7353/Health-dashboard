<template>
    <div class="dashboard">
        <Intro :intro="intro" :img="intro.img" />
        <Static :blog="blog" :img="blog.img" :type="blog.type" :amount="blog.amount" />
        <div class="linegraph">
            <h1>Hospital Survey</h1>
            <AreaChart/>
        </div>

        <div class="linechart d-flex justify-content-between align-items-center">
            <div class="linechart-item">
                <div class="text d-flex align-items-center justify-content-between">
                    <h1 class="text-title">$ 100 000</h1>
                    <p class="text-type">Income in current month</p>
                </div>
                <LineChartMonth/>
            </div>

            <div class="linechart-item">
                <div class="text d-flex align-items-center justify-content-between">
                    <h1 class="text-title">$ 25 000</h1>
                    <p class="text-type">Income in current week</p>
                </div>
                <LineChartweek/> 
            </div>

           
        </div>

         <Activity />

    </div>
</template>

<script>
import Intro from '@/components/Intro.vue'
import Static from '@/components/Static.vue'
import AreaChart from '@/components/AreaChart.vue'
import LineChartweek from '@/components/IncomeWeek.vue'
import LineChartMonth from '@/components/IncomeMonth.vue'
import Activity from '@/components/Activity.vue'



export default {
    name:'Dashboard',
    components:{
        Intro,
        Static,
        AreaChart,
        LineChartweek,
        LineChartMonth,
        Activity,

    },
    data(){
        return{
            intro:[
               { img: require('@/assets/profile.png')}
            ],

            blog:[
               { img: require('@/assets/static1.png'),
                 type: 'Appointments',
                 amount: '213'
               },

               { img: require('@/assets/static2.png'),
                 type: 'New Patients',
                 amount: '104'
               },

               { img: require('@/assets/static3.png'),
                 type: 'Operations',
                 amount: '12'
               },

               { img: require('@/assets/static4.png'),
                 type: 'Hospital Earnings',
                 amount: '$ 12.761'
               },
            ],

            
        }
    }
}
</script>

<style lang="scss">
.dashboard{
    background: #F6F8FB;
    max-width: 100%;
    padding-right: 30px;
}

.linegraph{
    background: white;
    padding: 24px;
    border-radius: 12px;
    padding-right: 25px;
}

.linechart{
    margin: 30px 0;
    gap: 24px;
  &-item{
      background: white; 
      padding:12px  24px;
      border-radius: 18px;  
      max-width: 100%;
      width: 520px; 

      .text{
          &-title{
                font-weight: bold;
                font-size: 20px;
                line-height: 26px;
                letter-spacing: 0.2px;
                color: #25282B;
          }

          &-type{
                font-weight: bold;
                font-size: 12px;
                line-height: 16px;
                text-align: right;
                letter-spacing: 0.1px;
                color: #A0A4A8;
          }
      }
  }
}
</style>