<script>
import Inner from './inner';
import WithSlot from './with-slot';

export default {
  name: 'Other',
  functional: true,
  render(createElement) {
    const inners = [1, 2, 3];

    return createElement('div',
      { class: 'container' },
      [
        'other',

        createElement(WithSlot, [
          createElement(Inner, {
            slot: 'foo'
          })
        ]),

        ...inners.map((el, index) => createElement(Inner, {
          key: index,

          // только для обычных компонентов
          ref: 'innerRef',
          refInFor: true
        }))
      ]
    );
  }
};
</script>

<style scoped>
  .container {
    padding: 24px;
    border-radius: 12px;
    border: 1px solid #2c3e50;
    width: 300px;
    display: flex;
    align-items: center;
    flex-direction: column;
    margin-bottom: 24px;
  }
</style>
