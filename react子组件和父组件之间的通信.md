```
React子组件和父组件通信包括以下几个方面：

1、子组件获取父组件属性：props或者state
2、子组件调用父组件的方法
3、父组件获取子组件的属性：props或者state
4、父组件调用子组件的方法
class Child extends Component{
    constructor(props) {
      super(props);

      this.state = {
        name:"ChildName2222"
      };
      this.getFatherName = this.getFatherName.bind(this);
    }

    static defaultProps = {
        ChildName: 'ChildName'
    }

    Fuc(){
        alert("调用子组件方法成功");
    }

    getName(){
        return "Props： " + this.props.ChildName + " , State: " + this.state.name;
    }

    getFatherName(){
        alert(this.props.father);
    }

    render(){
        console.log(this.props);
        // 调用父组件方法
        // 获取父组件的属性：props或者state
        return  <div>
                    <button onClick={this.getFatherName}>获取父组件的属性</button>
                    <button onClick={this.props.Fuc}>调用父组件方法</button>
                </div>;
    }
};

class Father extends Component{
    constructor(props) {
      super(props);
      this.state = {
        fatherName:"father"
      };
      this.runChildFuc = this.runChildFuc.bind(this);
      this.getChildName = this.getChildName.bind(this);
    }

    static defaultProps = {
        fatherName: 'father2222'
    }

    Fuc(){
        alert("调用父组件方法成功!");
    }

    runChildFuc(){
        this.refs["child"].Fuc();
    }

    getChildName(){
        alert(this.refs["child"].getName());
    }

    render(){
        console.log(this.state.fatherName);
        return  <div>
                    <button onClick={this.runChildFuc}>调用子组件方法</button>
                    <button onClick={this.getChildName}>获取子组件的属性</button>
                    <Child ref="child" father={"State: " + this.state.fatherName + ", Props: " + this.props.fatherName} Fuc={this.Fuc.bind(this)}></Child>
                </div>;
    }
};

export default Father;
```