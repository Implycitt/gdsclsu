<script lang="ts">
  import { onMount } from 'svelte';

  let { form } = $props();
</script>

<div class="grid min-h-dvh place-items-center gap-10 grid-template-rows-[auto]">
    <article>
        <div class="card card-body container mt-20 mb-5 justify-center align-center">
            <h1 class="text-5xl font-bold text-center mt-5 mb-10">Log In</h1>
            {#if form?.error}
                <div class="alert alert-danger alert-dismissible fade show" role="alert">
                    <span>{form.error}</span>
                </div>
            {/if}
            <form method="POST" action="?/login">
                <div class="mb-4">
                    <label for="email" class="form-label">Email</label>
                    <input type="email" name="email" id="email" class="form-control" placeholder="Email address" autocomplete="email" required />
                </div>
                <div class="mb-4">
                    <label for="password" class="form-label">Password</label>
                    <input type="password" class="form-control" name="password" id="password" placeholder="Enter password" autocomplete="new-password" required />
                </div>
                <input type="submit" value="Log In" class="btn text-white" />
            </form>
        </div>
    </article>
</div>