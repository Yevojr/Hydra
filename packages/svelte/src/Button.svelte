<script lang="ts">
  let { label = "Click me" }: { label?: string } = $props();
</script>

<button class="hydra-button">{label}</button>

<style>
  .hydra-button {
    background: var(--color-venom);
    color: var(--color-indigo);
    padding: var(--spacing-sm) var(--spacing-md);
    border: none;
    border-radius: 6px;
    font-weight: 600;
  }
</style>
