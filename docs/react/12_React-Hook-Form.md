# ![ ](../assets/react_light.svg#only-light) ![ ](../assets/react_dark.svg#only-dark) React Hook Form

React Hook Form is a library that makes handling forms in React **simpler and more efficient**. It minimizes re-renders, provides built-in validation, and works with both controlled and uncontrolled inputs.

## 1. Installation

```bash
npm install react-hook-form
```

## 2. Basic Usage

```jsx
import { useForm } from "react-hook-form";

function App() {
  const { register, handleSubmit } = useForm();

  const onSubmit = (data) => {
    console.log(data);
  };

  return (
    <form onSubmit={handleSubmit(onSubmit)}>
      <input {...register("username")} />
      <input type="password" {...register("password")} />
      <button type="submit">Submit</button>
    </form>
  );
}
```

* `register("fieldName")` connects input to the form
* `handleSubmit(onSubmit)` handles form submission
* `data` contains form values

## 3. Validation

Add validation rules directly in `register`.

```jsx
<input
  {...register("email", { required: true, pattern: /^\S+@\S+$/i })}
/>
```

Show error messages:

```jsx
const { register, handleSubmit, formState: { errors } } = useForm();

{errors.email && <p>Email is required and must be valid</p>}
```

## 4. Default Values

```jsx
const { register } = useForm({
  defaultValues: {
    username: "guest",
    age: 18
  }
});
```

## 5. Handling Different Inputs

```jsx
<select {...register("gender")}>
  <option value="male">Male</option>
  <option value="female">Female</option>
</select>

<input type="checkbox" {...register("subscribe")} />
```

## 6. Watching Values

```jsx
const { register, watch } = useForm();
const username = watch("username");

<p>Username: {username}</p>
```

## 7. Reset and Set Values

```jsx
const { register, handleSubmit, reset, setValue } = useForm();

reset({ username: "", password: "" }); // reset form

setValue("username", "JohnDoe"); // set field value manually
```

## 8. Form Submission with Async Code

```jsx
const onSubmit = async (data) => {
  const res = await fetch("/api", {
    method: "POST",
    body: JSON.stringify(data)
  });
  console.log(await res.json());
};
```

## 9. Benefits of React Hook Form

* Minimal re-renders (performance-friendly)
* Simple validation
* Easy integration with UI frameworks
* Works with both controlled & uncontrolled components
* Built-in error handling and helpers
