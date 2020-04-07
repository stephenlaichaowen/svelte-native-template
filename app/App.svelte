<page>
    <actionBar title="My App" />
    <stackLayout class="p-20">
      <label text="Tap the button" class="h1 text-center" />
      <button text="TAP" on:tap="{onTap}" class="-primary -active" />
      <button text="RESET" on:tap="{onReset}" class="-primary -active" />
      <label text={message} class="h2 text-center" textWrap="true" />
      <datePicker  />
      <Cool />
    </stackLayout>
</page>

<script>
  import Cool from './Cool.svelte'
    let counter = 42
    let message
    $: message = (counter <= 0)
                    ? "Hoorraay! You unlocked the Svelte-Native clicker achievement!"
                    : `${counter} taps left`

    function onTap() { counter-- }
    function onReset() {
      if (counter == 0) counter = 42
    }
   
</script>
