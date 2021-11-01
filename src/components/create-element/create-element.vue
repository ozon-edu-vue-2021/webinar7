<script>
import PropRender from './prop-render';

export default {
  name: 'CreateElement',
  functional: true,
  render(createElement) {
    return createElement('div',
      {
        class: 'container',
        style: {
          color: 'red'
        },
        attrs: {
          id: 'myDiv11'
        }
      },
      [
        'createElement',
        createElement(PropRender, {
          props: {
            foo: '1234',
            bar: 'asvkjsdvoiadbfo',
            baz: '222'
          }
        })
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
