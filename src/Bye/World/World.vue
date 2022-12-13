<script>
import { ref } from 'vue'

// cSpell:ignore wryyyyyyyyy
export default {
  name: 'World',
  setup() {
    const message = ref('wryyyyyyyyy')
    const say = () => `Dio: ${message.value}`
    return {
      message,
      say
    }
  }
}
</script>
