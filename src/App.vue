<template>
  <AppHeader />
  <div class="w-full flex" >
    <!-- <MoviesList /> -->
    <Calendar />
  </div>
  <AppFooter />
</template>
<script>
import AppHeader from "./components/AppHeader";
// import MoviesList from "./components/MoviesList";
import Calendar from "./components/Calendar";
import AppFooter from "./components/AppFooter";

export default {
  // components: { AppHeader, MoviesList, AppFooter }, //for movielist
  components: { AppHeader, Calendar, AppFooter },
}
</script>


