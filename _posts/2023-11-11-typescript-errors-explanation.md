```
Cannot redeclare block-scoped variable 'car1'.ts(2451) //

Variable declaration list cannot be empty.ts(1123)

Type '{ name: string; id: string; height: any; }' is not assignable to type 'Box'.
  Object literal may only specify known properties, and 'name' does not exist in type 'Box'.

Type 'string' is not assignable to type 'number'.ts(2322)
practice.ts(5, 5): The expected type comes from property 'length' which is declared here on type 'Box'
(property) Box.length: number

Element implicitly has an 'any' type because expression of type 'string' can't be used to index type 'Box'.
  No index signature with a parameter of type 'string' was found on type 'Box'.ts(7053)
(parameter) box: Box

const res = (string | number)[]

Property 'name' of type 'string | undefined' is not assignable to 'string' index type 'string | number'.ts(2411)
(property) Box.name?: string | undefined

```
