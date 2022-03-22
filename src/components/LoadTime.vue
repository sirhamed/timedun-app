<template>
    <div class="timedun-box">
        <h2>Timedun</h2>
        <div class="timedun-item">
            <p class="timedun-text">Day: {{dayOfTheYear}}th </p>
            <div class="progress" style="height: 3px">
                <div class="progress-bar bg-danger" role="progressbar" style= "width: + perce" aria-valuenow="70" aria-valuemin="0" aria-valuemax="365"></div>
            </div>
        </div>
        <div class="progress-item">
            <p class="timedun-text">Percent: {{percentageOfYear}}%</p>
            <div class="progress" style="height: 3px">
                <div class="progress-bar bg-success" role="progressbar" style= "width: 19%" v-bind:aria-valuenow="19" aria-valuemin="0" aria-valuemax="100"></div>
            </div>
        </div>
        <p class="sign">Developed by <a href="www.instagram.com/yek-hamed">Yek Hamed</a> in 2022</p>
    </div>
</template>

<script>
export default {
    data(){
        return{
            dayOfTheYear: '',
            percentageOfYear: '',
        }
    },

    created(){
        //Get current date to calculate day of the year
        var currentDate = new Date();
        console.log("Local Time: " + currentDate);

        this.getCurrentTime(currentDate)
    },
    methods:{
        getCurrentTime(getcurrentDate){
        var currentDate = getcurrentDate;
        var newCommit = 0;
        //Khiar avali dovom Dovomi

        var clcDays = 0;
        var percentYear = 0;
        var listOfMonths = [31,28,31,30,31,30,31,31,30,31,30,31];

        for (var i = 0; i < currentDate.getMonth(); i++)
            clcDays += listOfMonths[i];

        clcDays += currentDate.getUTCDate();
        percentYear = clcDays/365 * 100;

        this.dayOfTheYear = clcDays;
        this.percentageOfYear = percentYear.toFixed();
        }
    }
}
</script>

<style>
    .timedun-box{
        width: 400px;
        border-radius: 3px;
        margin: auto;
        padding: 70px 50px 25px 50px;
        box-sizing: border-box;
        background-color: rgb(241, 240, 240);
        box-shadow: 2px 2px 15px  rgb(87, 87, 87);
    }

    h2{
        font-family: Helvetica, sans-serif;
        font-size: 25px;
        font-weight:bolder;
        box-sizing: content-box;
        margin-bottom: 50px;
    }

    .timedun-item{
        box-sizing: content-box;
        padding-bottom: 12px;
        margin-bottom: 35px;
    }
    .timedun-text{
        font-family: Helvetica, sans-serif;
        font-size: 13px;
        font-weight: 500;
        /* background-color:blueviolet */
    }

    .sign, a {
        margin-top: 80px;
        font-family: Tahoma;
        font-size: 11px;
        box-sizing: content-box;
        padding-bottom: 14px;
        text-decoration: none;
    }
</style>