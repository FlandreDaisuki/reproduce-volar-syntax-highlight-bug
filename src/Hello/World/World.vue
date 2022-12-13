<script>
import { ref, computed, onMounted } from 'vue'

// cSpell:ignore wryyyyyyyyy
export default {
  name: 'World',
  setup() {
    const message = ref('wryyyyyyyyy')
    const who = ref('Dio')
    onMounted(() => {
      message.value = 'yare yare daze'
      who.value = 'jo- ta ro-'
    })
    const somethingToSay = computed(()=>`${who.value}: ${message.value}`)
    const say = () => somethingToSay.value

    return {
      message,
      say
    }
  }
}
</script>

