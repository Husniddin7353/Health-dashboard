<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  name:'LineChartweek',
  mounted() {
    this.renderChart(
      {
        labels: [
          "21 July",
          "22 July",
          "23 July",
          "24 July",
          "25 July",
          "26 July",
          "27 July"
        ],
        datasets: [
          {
            label: "Current Week",
            data: [69000, 63000, 73000, 71000, 79000, 69000, 72030],
            backgroundColor: "transparent",
            borderColor: "#FAC032",
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