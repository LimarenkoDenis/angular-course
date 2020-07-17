
[Join invisionapp - for more details](https://projects.invisionapp.com/freehand/document/fFJOdvSSK)


![GitHub Logo](/classroom/classroom.png)


- Overview, components
    - header, footer components
    - product list with list of cards 
    ```
        <card></card>
        <card></card>
        <card></card>
    ```
    - Component Dev Kit Module with Exports: 
        - Card (product)
        - Logo Component

- Template Syntax 
    - card component
        hardcode and display data
        ```
            {
                "id": 0,
                "title": "Iнжир в шоколадi",
                "description": "На фото наша цукерка з цілого інжиру з горіхом макадамия в чорному шоколаді та з крихтою помело",
                "photo": "https://static.tildacdn.com/tild3662-3233-4635-b133-663735363364/80718754_61885090535.jpg",
                "price": 30,
                "type": "candy",
                "created": "Sat Aug 31 2019 16:11:42 GMT+0300 (Eastern European Summer Time)"
            }
        ```
    - Events 
        - Buy and Info clicks

- Input, Output
    - Move data to product list and use Input


    ```
        <card [product]="products[0]"></card>
        <card [product]="products[0]"></card>
        <card [product]="products[0]"></card>
    ```
    
    - By clicking to BUY - output event
    ```
        <card [product]="products[0]" (buy)="buy($event)"></card>
        <card [product]="products[0]" (buy)="buy($event)"></card>
        <card [product]="products[0]" (buy)="buy($event)"></card>
    ```
    


- Directives
    - 3 types



- Pipes
    Default 



- Custom Directive and Pipe
    - Pipes
        - Filter pipe for products by name and description
    - Directives
        - Acl (Add Admin Menu item and show/hide if flag in LocalStorage)



- Reactive Rxjs



- Service 
 - Add Products and Card Service
 - Implement fetch products and add to Cart 



- HTTP
 - json-server
 ```
   data here ...
 ```
