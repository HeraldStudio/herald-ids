<script>
import { async } from 'q';

export default {
  fetch(context){
    let {platform, verifyToken} = context.params
    context.redirect(`https://newids.seu.edu.cn/authserver/login?service=http://auth.myseu.cn/verify/${platform}/${verifyToken}`)
  }
}
</script>