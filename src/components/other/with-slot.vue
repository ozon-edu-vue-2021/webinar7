<script>
export default {
  name: 'WithSlot',
  functional: true,
  render(createElement, { scopedSlots }) {
    return createElement('i', [
      scopedSlots.foo && scopedSlots.foo()
    ]);
  }
};
</script>
