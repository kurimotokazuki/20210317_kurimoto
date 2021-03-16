<script>
import axios from "axios";
export default {
  async created() {
    const item = await axios.get(
      `https://apis.postcode-jp.com/api/v4=${this}&units=metric&appid=pqwM3Gcq2bmiysVFgSb49oOX12AuPT3yeJIC05Q`
    );
      const weatherData = item.data;
    this.name = weatherData.name;
    this.main = weatherData.weather[0].main;
    this.temp = weatherData.main.temp;
    this.humidity = weatherData.main.humidity;
    this.speed = weatherData.wind.speed;
  },
}

</script>