<script type="application/javascript"
           src="https://cdn.jsdelivr.net/npm/@masa-finance/analytics-sdk@latest/dist/browser/masa-analytics.min.js"></script>
    
  <script>
    var clientId = "b821def8-8d44-44c0-9923-c8a005ba2dac";
    var clientApp = "Cryptomatic";
    var clientName = "Cryptomancy";
    
    var masaAnalytics = new MA.MasaAnalytics({ clientApp, clientName, clientId });;
  
    var page = window.location.href;
  
    // Add an event listener to ensure the script is loaded before calling its functions
    window.onload = function() {
      // Track page view event for initial load
      masaAnalytics.firePageViewEvent({ page });
  
      // This function is called every time a "page view" happens in SPAs, i.e., when the route changes
      function trackPageViewForSPA() {
        var updatedPageUrl = window.location.href;
        masaAnalytics.firePageViewEvent({ page: updatedPageUrl });
      }
  
      // This event is triggered when the route changes in many SPAs
      window.addEventListener("popstate", trackPageViewForSPA);
    };
  </script>
