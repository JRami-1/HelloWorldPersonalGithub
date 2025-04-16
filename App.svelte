<script>
    import Router from 'svelte-spa-router';
    import { push, pop, replace } from 'svelte-spa-router';
  
    import DisclaimerBanner from './components/DisclaimerBanner.svelte';
    import Header from './components/Header.svelte';
    import Navigation from './components/Navigation.svelte';
    import Home from './components/Home.svelte';
    import ListingDetail from './components/ListingDetail.svelte';
    import AboutPage from './components/AboutPage.svelte';
    import Login from './components/Login.svelte'
    
    // Define routes
    const routes = {
      '/': Home,
      '/listings/:id': ListingDetail,
      '/about': AboutPage,
      '/login': Login
    };
    
    // Function to navigate to listing detail
    function goToListing(id) {
      push(`/listings/${id}`);
    }
    
    // Function to navigate to about page
    function goToAbout() {
      push('/about');
    }
    
    // Function to navigate to home
    function goToHome() {
      push('/');
    }
  
    // Function to navigate to Login
    function goToLogin() {
      push('/login');
    }
  </script>
  
  <DisclaimerBanner />
  <Header />
  <Navigation {goToHome} {goToAbout} {goToLogin}/>
  
  <main>
    <Router {routes} />
  </main>
  
  <style>
    :global(body) {
      font-family: Arial, sans-serif;
      background-color: #f9f9f9;
      margin: 0;
      padding: 0;
      color: #4a4a4a;
    }
    
    main {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }
  </style>  