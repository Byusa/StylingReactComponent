# StylingReactComponent
Styling React component with conditional and dynamic styles 
  1. inline styling
  ```
 //inline styling with dynamic styling
  style={{ borderColor: !isValid ? 'red' : '#ccc', background: !isValid ? 'salmon' : 'transparent'}}  

/* adding a setting styles dynamically */
  <div className={`form-control ${!isValid ? 'invalid' : ''}`}>
    <label style={{color: !isValid ? 'red' : 'black'}}>Course Goal</label>
    <input type="text" onChange={goalInputChangeHandler}/>
  </div>
```
  2. Styled components
  ```
    import styled from 'styled-components';

  const FormControl = styled.div`
    margin: 0.5rem 0;

  & label {
    font-weight: bold;
    display: block;
    margin-bottom: 0.5rem;
    color: ${props => props.invalid ? 'red' : 'black'};
  }

  & input {
    display: block;
    width: 100%;
    border: 1px solid ${props => (props.invalid ? 'red' : '#ccc')};
    background: ${props => (props.isValid ? '#ffd7d7' : 'transparent' )};
    font: inherit;
    line-height: 1.5rem;
    padding: 0 0.25rem;
  }

  & input:focus {
    outline: none;
    background: #fad0ec;
    border-color: #8b005d;
  }

    @media (mid-width: 768px) {
      width: auto;
    }

 `;
 //the use
   <FormControl className={!isValid && 'invalid’}/> 
  ```
  3. css Modules

```
    //first name it with module => Button.module.css

  import styles from 'styled-components';

  const Button = props => {
    return (
      <button type={props.type} className={styles.button} onClick={props.onClick}>
        {props.children}
      </button>
    );
  };
```

