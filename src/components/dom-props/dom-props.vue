<script>
import PropRender from '../create-element/prop-render';

export default {
  name: 'DomProps',
  functional: true,
  render(createElement) {
    return createElement('div',
      { class: 'container' },
      [
        'domProps',
        createElement('span', {
          domProps: {
            innerHTML: '<i>some italic text asda as</i> <script>alert("alert!!";)<\\/script>' // important to sanitize
          }
        }),
        createElement('input', {
          domProps: {
            value: 'input value'
          }
        }),
        createElement(PropRender, {
          domProps: {
            innerHTML: '<b>should not work</b>'
          }
        })
      ]
    );
  }
};



// <script>alert("alert!!";)<\/script>
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
