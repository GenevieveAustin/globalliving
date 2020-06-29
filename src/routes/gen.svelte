<script>
  import { stores } from "@sapper/app"
  const { session } = stores()
  let name = ""
</script>

<style>

</style>

<h1>{session.user}</h1>
