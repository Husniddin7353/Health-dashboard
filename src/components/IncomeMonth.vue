<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  name:'LineChartMonth',
  mounted() {
    this.renderChart(
      {
        labels: [
          "1 July",
          "8 July",
          "16 July",
          "23 July",
          "31 July",
          
        ],
        datasets: [
          {
            label: 'Current Month',
            data: [69000, 63000, 73000, 71000, 79000, 69000, 72030],
            backgroundColor: "transparent",
            borderColor: "#336CFB",
            pointBackgroundColor: "white"
          }
        ]
      },
      {
        responsive: true,
        maintainAspectRatio: false,
        title: {
          display: true,
         
        }
      }
    );
  }
};
</script>