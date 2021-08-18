
<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  data() {
    return {
      gradient: null,
      gradient2: null
    };
  },
  mounted() {
    this.gradient = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 450);
    this.gradient2 = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 450);

    this.gradient.addColorStop( 0, "rgba(51, 108, 251, 0.9)");
    this.gradient.addColorStop(0.5, "rgba(51, 108, 251, 0.25)");
    this.gradient.addColorStop(1, " rgba(51, 108, 251, 0)");



    this.renderChart(
      {
        labels: [
          "2020-1",
          "2020-2",
          "2020-3",
          "2020-4",
          "2020-5",
          "2020-6",
          "2020-7",
          "2020-8",
          "2020-9",
          "2020-10",
          "2020-11",
          "2020-12",
        ],
        datasets: [
          {
            label: "Patient 2020",
            borderColor: "#336CFB",
            borderSize: "5px",
            pointBackgroundColor: "white",
            borderWidth: 2,
            pointBorderColor: "#336CFB",
            backgroundColor: this.gradient,
            data: [150, 140, 130, 120, 130, 150, 160, 150 , 130, 145, 160, 180]
          },
          {
            label: "Patient 2019",
            pointBorderColor: "#FAC032",
            pointBackgroundColor: "white",
            borderColor: "#FAC032",
            borderWidth: 2,
            backgroundColor: "transparent",
            data: [150, 130, 120, 150, 130, 160, 140, 120 , 150, 130, 155, 160]
          }
        ]
      },
      { responsive: true, maintainAspectRatio: false }
    );
  }
};
</script>
