<script>
import Emitter from './emitter';

export default {
  name: 'Listener',
  functional: true,
  render(createElement) {
    const handler = () => { console.log('click'); };
    const handlerCapture = () => { console.log('!click'); };
    const handlerOnce = () => { console.log('~click'); };
    const handlerNative = () => { console.log('click native'); };

    return createElement('div',
      { class: 'container' },
      [
        'listeners',
        createElement(Emitter, {
          on: {
            click: handler,
            '!click': handlerCapture,
            '~click': handlerOnce,
            myClick: handler,
          },
          nativeOn: {
            click: handlerNative
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
