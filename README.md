1.建立一個todolist module

2.建立一個todolist component

3.CLI  import 了 TodoListComponent 進來，並將其加到 TodoListModule 的 Metadata 裡，讓 Angular 知道 TodoListComponent 是 TodoListModule 裡面的

4.todo-list.component.ts中的selector會改為app-todo-list 然後去app.component.html中貼上該標籤<app-todo-list></app-todo-list>

5.會報錯 先確認是不是當前module的一部分
<app-todo-list></app-todo-list>是放在app.component.html 裡，所以它所屬的 Module 就是 AppModule

6.檢查AppModule發現沒引用進來 加入:
import { TodoListModule } from './todo-list/todo-list.module';

在@NgModule內imports加入TodoListModule

7.檢查todo-list.moduler發現沒有export

在@NgModule內新增 exports: [TodoListComponent]

8.總結 
在todo-list.component中有<p>todo-list works!</p>

todo-list.module會將TodoListComponent export出去

app.module引入TodoListModule之後 在app.component的<app-todo-list></app-todo-list>就可以渲染出<p>todo-list works!</p>