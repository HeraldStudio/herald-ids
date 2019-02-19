<script>
import { async } from 'q';
import axios from 'axios';

export default {
  components: {
  },
  async asyncData(context){
      context.redirect('heraldApp://login')
  },
  head () {
    return {
      title:'跳转中'
    }
  }
}
</script>