# project9
intial draft of project9
<!doctype html>
<html ng-app>
<head>
  <title> angular app</title>
  <link href="styles/animations.css" rel="stylesheet"/> 
</head>
<body ng-init="Customers=['Ted', 'Michelle', 'Zed']">
<h1> angularjs in 20-ish minutes</h1>
    <div ng-view class="slide-animation"> </div> 

  <div> 
      search:<input type="text" ng-model="searchText"/>
       <br />
       <h3> Customers:</h3>
       <table>
           <trng-repeat="cust in customers |filter:searchText ">
               <td>{{cust.name }}  </td>
               <td>{{cust.total currency }}  </td>
           </tr>
       </table>
  </div> 
  <script src="js/anjular.js"></script> 
  <script src="js/anjular-route.js"></script> 
  <script src="js/anjular-animation.js"></script> 
   <script>
    var app= anjular.module('customersApp',['ngRoute', 'ngAnimation']);

     app.config(function($routeprovider){
         $RouteProvider.when('/',
         {
              controller:'OrdersController',
              TemplaterUrl:'app/view/orders.html'
         })

         .when('/orders',
         {
              controller:'OrdersController',
              TemplaterUrl:'app/view/orders.html'
         })
     });

    app.comtroller('Customerscontroller', function($scope){
    $scope.customers =[
        {"id": 1, "name": "Ted", "total" :5.996},
        { "id": 2, "name": "Michelle", "total" :10.994},
        { "id": 3, "name": "Zed", "total" :10.99},
        { "id": 4, "name": "Tina", "total" :15.994}
      ];
    }); 

    

    var app= anjular.module('customersApp',['ngRoute']);
    app.comtroller('Customerscontroller', function($scope){
    $scope.customers =[
        {"id": 1, "name": "Ted", "total" :5.996},
        { "id": 2, "name": "Michelle", "total" :10.994},
        { "id": 3, "name": "Zed", "total" :10.99},
        { "id": 4, "name": "Tina", "total" :15.994}
      ];
    }); 

    app.comtroller('Customerscontroller', function($scope){
    $scope.customerID=5;
    });

    app.comtroller('Customerscontroller', function($scope){
       function init(){

          cunstomersFactory.getCustomers().success(function(data))
               $scope.customers=data;
          });
        }
          init();
       });
    
app.factory('Customersfactory', function($scope){
    var factory={};
     factory.getCustomers=function(){
          return $http.get('/customers.json');
      };
      return factory;
    }); 
     
   /<script>
</body>
</html>
