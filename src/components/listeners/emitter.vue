<script>
export default {
  name: 'Emitter',
  functional: true,
  render(createElement, { listeners }) {
    return createElement('div', {
      on: {
        click: listeners.click,
        '!click': listeners['!click'],
        '~click': listeners['~click']
      }
    }, [
      'click me!',
      createElement('div', {
        on: {
          click: listeners.myClick
        }
      })
    ]);
  }
};
</script>

<style scoped>
  .container {
    padding: 24px;
    border-radius: 12px;
    border: 1px solid #2c3e50;
    width: 300px;
  }
</style>
