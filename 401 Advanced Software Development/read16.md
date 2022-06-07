# Spring Authentication

- Spring Security has an architecture that is designed to separate authentication from authorization and has strategies and extension points for both.

- **authentication** (who are you?) and **authorization** (what are you allowed to do?).

- Spring Security in the web tier is currently tied to the Servlet API, so it is only really applicable when running an application in a servlet container, either embedded or otherwise. It is not, however, tied to Spring MVC or the rest of the Spring web stack, so it can be used in any servlet application — for instance, one using JAX-RS.

- It is not uncommon to combine Web security and method security. The filter chain provides the user experience features, such as authentication and redirect to login pages and so on, and the method security provides protection at a more granular level.

# Spring Auth Cheat Sheet

## Step 1: set up a user model and repo

## Step 2: create a controller for that model

## Step 3: UserDetailsServiceImpl implements UserDetailsService

gets a User from the database by username (make sure your repository has the method to make this easy!)

## Step 4: ApplicationUser implements UserDetails

use IntelliJ to implement the methods; make the boolean ones all return true

## Step 5: WebSecurityConfig extends WebSecurityConfigurerAdapter

- has a UserDetailsService
- passwordEncoder bean
- configure AuthManagerBuilder
  - `auth.userDetailsService(userDetailsService).passwordEncoder(passwordEncoder());`
- configure HttpSecurity
  - cors? csrf?
  - matchers for URLs that are allowed
    - ensure that login and signup URLs allowed; also consider homepage etc.
  - formLogin with login page set up
  - logout

```
    @Override
    @Bean
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManagerBean();
    }
```

## Step 6: registration page

- create it w/ form
- ensure it posts to a route your controller is ready for
- check it's saving in the DB

```
    // maybe autologin?
    Authentication authentication = new UsernamePasswordAuthenticationToken(newUser, null, new ArrayList<>());
    SecurityContextHolder.getContext().setAuthentication(authentication);
```

## Step 7: login page

- create it w/ form
- ensure it posts to the route you specified in web config
- try it out!
- add to a template w/ things about the Principal.





## Reference and Citation

> Hambalieu Jallow <