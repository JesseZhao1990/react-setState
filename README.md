# react 的setState方法

###提问1：当用setState设置state的值之后，里面打印state，state改变了吗？

没有改变，setState是异步的。


      export default class Test React.Componet{
        constructor(props){
          super(props);
          this.state={test:"this is a test"}
        }

        changeState=()=>{
            this.setState({test:"state changed"});
            console.log(this.state.test);
        }

        render(){
          return(
            <div>
            <button onClick={this.changeState}>点击测试</button>
            </div>
          )
        }
      }
      
      
解决办法可以通过setState的回调方法来保证state改变之后再干一些事情

      export default class Test React.Componet{
        constructor(props){
          super(props);
          this.state={test:"this is a test"}
        }

        changeState=()=>{
            this.setState({test:"state changed"},()=>{
              console.log(this.state.test);
            });
        }

        render(){
          return(
            <div>
            <button onClick={this.changeState}>点击测试</button>
            </div>
          )
        }
      }
