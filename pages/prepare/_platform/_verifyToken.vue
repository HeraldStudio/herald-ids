<script>
import { async } from 'q';
import urlencode from 'urlencode'
export default {
  fetch(context){
    let {platform, verifyToken} = context.params
    let targetUrl = urlencode(`http://auth.myseu.cn/verify/${platform}/${verifyToken}`)
    context.redirect(`https://newids.seu.edu.cn/authserver/login?service=${targetUrl}`)
  }
}
</script>