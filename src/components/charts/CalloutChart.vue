<script>
import { Line } from 'vue-chartjs'

export default Line.extend({
  props: ['data', 'height','bordercolor', 'width', 'variant'],
  mounted () {
    this.renderChart({
      labels: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'],
      datasets: [
        {
          backgroundColor: 'transparent',
          borderColor: this.bordercolor,
          data: this.data
        }
      ]
    }, {
      responsive: true,
      maintainAspectRatio: false,
      scales: {
        xAxes: [{
          display: false
        }],
        yAxes: [{
          display: false
        }]
      },
      elements: {
        line: {
          borderWidth: 2
        },
        point: {
          radius: 0,
          hitRadius: 10,
          hoverRadius: 4,
          hoverBorderWidth: 3
        }
      },
      legend: {
        display: false
      }
    })
  }
})
</script>
