<script lang="jsx">
import Inner from './inner';
import PropRender from '../create-element/prop-render';
import WithSlot from '../other/with-slot';

export default {
  name: 'JSX',
  functional: true,
  render() {
    const flag = true;
    const arr = [1, 2, 3];
    const ChosenComponent = flag ? Inner : PropRender;
    const handler = () => {console.log('click');};

    const conditionalRender = () => {
      if (flag) {
        return <Inner />;
      }
    };

    return (<div class="container">
      {conditionalRender()}
      {flag ? <Inner /> : null}
      {...(flag ? [<Inner />] : [])}

      <ChosenComponent
        chosen={1}
        on={{ click: handler }}
      />

      {...arr.map(el => <PropRender customProp={el} />)}

      <WithSlot>
        <Inner slot="foo" />
      </WithSlot>
    </div>);
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
