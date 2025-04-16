import Home from './components/Home.svelte';
   import ListingDetail from './components/ListingDetail.svelte';
   import AboutPage from './components/AboutPage.svelte';
   import SkillSharing from './components/SkillSharing.svelte';
   
   // Define routes
   const routes = {
     '/': Home,
     '/listings/:id': ListingDetail,
     '/about': AboutPage
     '/about': AboutPage,
     '/skill-sharing': SkillSharing
   };
   
   // Function to navigate to listing detail
 @@ -30,11 +32,15 @@
   function goToHome() {
     push('/');
   }
   // Function to navigate to skill sharing page
   function goToSkillSharing() {
     push('/skill-sharing');
   }
 </script>
 
 <DisclaimerBanner />
 <Header />
 <Navigation {goToHome} {goToAbout} />
 <Navigation {goToHome} {goToSkillSharing} {goToAbout} />
 
 <main>
   <Router {routes} />