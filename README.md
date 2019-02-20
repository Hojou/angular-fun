# Cheat sheet

# MVP & Components

## Binding and interpolation
Property binding:
```
<input [value]="myVariable">
```

Interpolation:
```
<div>{{ myVariable }}</div>
```

## Templates
```
<div *ngFor="let item of itemCollection">{{ item.name }}</div>
<div *ngIf="showMe">Show this if showMe is true</div>
```

# Services, providers and DI

```
constructor(service1: ServiceOne, private service2: ServiceTwo, public service3: ServiceThree) {
    // Access too all three services
}

someFunction() {
    // Access to service2 and service3
}

// service3 will be accessible in the html template as well as derived classes.
```

# Observables

```
{{ observable$ | async | json }}

observable$.pipe(
    map(o => o.someNumberProperty),
    filter(n => n > 5),
    take(5)
).subscribe(number => {
    console.log('received a number', number)
});

const streamOfData$ = urlsToQuery$.pipe(
    flatMap(url => requestDataFrom(url)
));
```
Noteworthy: switchMap


# Links
https://angular.io/

https://rxmarbles.com/

