### joi
---
https://github.com/hapijs/joi

```js
const Joi = require('joi');

const schema = Joi.object().keys({
  username: Joi.string().alphanum().min(3).max(30).required(),
  password: Joi.string().regex(/^[a-zA-Z0-9]{3,30}$/),
  access_token: [Joi.string(), Joi.number()],
  birthyear: Joi.number().integer().min(1900).max(2013),
  email: Joi.string().email({ minDomainAtoms: 2 })
}).with('username', 'birthyear').without('password', 'access_token');

const result = Joi.validate({ username: 'abc', birthyear: 1994}, schema);

const result = Joi.validate({ username: 'abc', birthyear: 1994 }, schema);

Joi.validate({ username: 'abc', birthyear: 1994 }, schema, function (err, value) { });


const schema = {
  a: Joi.string()
};

const {error, value} = Joi.validate({ a: 'a string' }, schema);
Joi.validate({ a: 'a string' }, schema, function (error, value){ });

const schema = Joi.string().min(10);

const schema = Joi.object().keys({
  a: Joi.string()
});

Joi.validate(undefined, Joi.string());

Joi.validate(undefined, Joi.string().required());
Joi.validate(undefined, Joi.string(), { presence: "required" });
```

```
```
