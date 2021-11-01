<script>
export default {
  name: 'PropRender',
  functional: true,
  render(createElement, { props }) {
    return createElement('div', [
      ...Object.entries(props).map(([key, val]) => createElement('span', [
        `${key} - ${val}`,
        createElement('br')
      ]))
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
