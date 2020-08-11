<script>
  import { stores } from "@sapper/app"
  const { session } = stores()
  let name = ""
</script>

<style>

</style>

<h1> Name: {session.user}</h1>
<h1> Year Level: {session.year}</h1>
<h1> Class Selection: {session.class}</h1>
