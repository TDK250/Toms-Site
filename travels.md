---
layout: default
title: Travels
---

<div class="hero">
  <h1>My Travel Adventures</h1>
  
  <div class="travel-stats">
    <div class="stat-item">
      <div class="stat-number">22</div>
      <div class="stat-label">Countries</div>
    </div>
    <div class="stat-item">
      <div class="stat-number">106</div>
      <div class="stat-label">Places</div>
    </div>
    <div class="stat-item">
      <div class="stat-number">3</div>
      <div class="stat-label">Continents</div>
    </div>
  </div>
</div>

<section class="content-section">
  
  <!-- Interactive Map -->
  <div class="map-section">
    <div class="map-header">
      <h3 class="map-title">
        <i data-feather="map" class="icon"></i>
        Interactive Travel Map
      </h3>
    </div>
    <div id="map"></div>
  </div>

  <!-- Navigation Tabs -->
  <div class="tab-navigation">
    <button class="tab-button active" onclick="showTab('countries')">
      <i data-feather="globe" class="icon"></i>
      By Countries
    </button>
    <button class="tab-button" onclick="showTab('trips')">
      <i data-feather="calendar" class="icon"></i>
      By Trips
    </button>
  </div>

  <!-- Travel by Trips -->
  <div class="travels-container" id="trips-tab" style="display: none;">
    <h2>Travels by Trips</h2>
    <div id="trips-container"></div>
  </div>

  <!-- Travel by Countries -->
  <div class="travels-container" id="countries-tab">
    <h2>Travels by Countries</h2>
    <div id="continents-container"></div>
  </div>

</section>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.css" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.js"></script>

<style>
/* Travel Page Styles - Consistent with site design */
.hero {
  text-align: center;
  padding: 3rem 0;
  margin-bottom: 3rem;
}

.hero h1 {
  margin-bottom: 1rem;
  color: var(--text-primary);
}

.hero p {
  font-size: 1.2rem;
  color: var(--text-secondary);
  max-width: 600px;
  margin: 0 auto 2rem;
}

.travel-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  max-width: 500px;
  margin: 0 auto;
}

.stat-item {
  background: var(--bg-secondary);
  border: 1px solid var(--border);
  border-radius: 0.75rem;
  padding: 1.5rem 1rem;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.stat-item:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 25px var(--shadow-hover);
}

.stat-number {
  font-size: 2rem;
  font-weight: bold;
  color: var(--accent);
  margin-bottom: 0.5rem;
  display: block;
}

.stat-label {
  font-size: 0.9rem;
  color: var(--text-secondary);
  font-weight: 500;
}

.content-section {
  margin-bottom: 3rem;
}

/* Map Section - Matches site card styling */
.map-section {
  background: var(--bg-secondary);
  border: 1px solid var(--border);
  border-radius: 0.75rem;
  overflow: hidden;
  margin-bottom: 3rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.map-section:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px var(--shadow-hover);
}

.map-header {
  background: var(--bg-primary);
  padding: 1.5rem;
  border-bottom: 1px solid var(--border);
  text-align: center;
}

.map-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
  margin: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

#map {
  height: 500px;
  width: 100%;
}

/* Tab Navigation */
.tab-navigation {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 2rem;
  justify-content: center;
}

.tab-button {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.5rem;
  border: 1px solid var(--border);
  background: var(--bg-secondary);
  color: var(--text-primary);
  border-radius: 0.5rem;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 500;
  transition: all 0.2s ease;
}

.tab-button:hover {
  background: var(--bg-primary);
  transform: translateY(-1px);
}

.tab-button.active {
  background: var(--accent);
  color: white;
  border-color: var(--accent);
}

.tab-button .icon {
  width: 18px;
  height: 18px;
}

/* Travels Container */
.travels-container {
  margin-bottom: 3rem;
}

.travels-container h2 {
  text-align: center;
  margin-bottom: 2rem;
  color: var(--text-primary);
}

/* Trip Sections */
.trip-section {
  background: var(--bg-secondary);
  border: 1px solid var(--border);
  border-radius: 0.75rem;
  margin-bottom: 1.5rem;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.trip-section:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px var(--shadow-hover);
}

.trip-header {
  background: var(--bg-primary);
  padding: 1rem 1.5rem;
  border-bottom: 1px solid var(--border);
}

.trip-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
  margin: 0 0 0.25rem 0;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.trip-title .icon {
  width: 20px;
  height: 20px;
  color: var(--accent);
}

.trip-date {
  font-size: 0.9rem;
  color: var(--text-secondary);
  margin-bottom: 0.25rem;
}

.trip-summary {
  font-size: 0.875rem;
  color: var(--text-secondary);
}

.trip-places {
  padding: 1.5rem;
  display: grid;
  gap: 1rem;
}

.trip-country {
  background: var(--bg-primary);
  border: 1px solid var(--border);
  border-radius: 0.5rem;
  overflow: hidden;
}

.trip-country-header {
  padding: 0.75rem 1rem;
  font-weight: 600;
  color: var(--text-primary);
  background: var(--bg-secondary);
  border-bottom: 1px solid var(--border);
}

.trip-cities {
  padding: 1rem;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 0.5rem;
}

/* Continent Sections - Match site card styling */
.continent-section {
  background: var(--bg-secondary);
  border: 1px solid var(--border);
  border-radius: 0.75rem;
  margin-bottom: 1.5rem;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.continent-section:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px var(--shadow-hover);
}

.continent-header {
  background: var(--bg-primary);
  padding: 1rem 1.5rem;
  border-bottom: 1px solid var(--border);
}

.continent-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
  margin: 0;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.continent-title .icon {
  width: 20px;
  height: 20px;
  color: var(--accent);
}

.country-count {
  font-size: 0.875rem;
  color: var(--text-secondary);
  margin-left: 0.5rem;
}

.countries-grid {
  padding: 1.5rem;
  display: grid;
  gap: 1rem;
}

/* Country Items - Consistent with site interactive elements */
.country-item {
  background: var(--bg-primary);
  border: 1px solid var(--border);
  border-radius: 0.75rem;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.country-item:hover {
  transform: translateY(-1px);
}

.country-button {
  width: 100%;
  text-align: left;
  padding: 1rem 1.5rem;
  background: none;
  border: none;
  cursor: pointer;
  transition: background-color 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: var(--text-primary);
}

.country-button:hover {
  background: var(--bg-secondary);
}

.country-name {
  font-weight: 600;
  font-size: 1.1rem;
}

.country-info {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.place-count {
  font-size: 0.875rem;
  color: var(--text-secondary);
}

.expand-arrow {
  transition: transform 0.2s ease;
  color: var(--accent);
  font-size: 1.2rem;
}

.expand-arrow.expanded {
  transform: rotate(90deg);
}

.cities-container {
  background: var(--bg-secondary);
  display: none;
  padding: 1.5rem;
  border-top: 1px solid var(--border);
}

.cities-container.expanded {
  display: block;
}

.cities-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 0.75rem;
}

.province-section {
  margin-bottom: 1.5rem;
}

.province-header {
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 0.75rem;
  padding: 0.5rem 1rem;
  background: var(--bg-primary);
  border-radius: 0.5rem;
  border: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.province-count {
  font-size: 0.875rem;
  color: var(--text-secondary);
  font-weight: normal;
}

.city-tag {
  background: var(--accent);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 1rem;
  font-size: 0.875rem;
  text-align: center;
  font-weight: 500;
  transition: all 0.2s ease;
}

.city-tag:hover {
  transform: translateY(-1px);
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.icon {
  width: 18px;
  height: 18px;
  stroke: currentColor;
  stroke-width: 2;
  fill: none;
  stroke-linecap: round;
  stroke-linejoin: round;
}

/* Mobile Responsive - Consistent with site patterns */
@media (max-width: 768px) {
  .hero {
    padding: 2rem 1rem;
  }
  
  .hero h1 {
    font-size: 2rem;
  }
  
  .travel-stats {
    grid-template-columns: repeat(3, 1fr);
    gap: 0.75rem;
  }
  
  .stat-item {
    padding: 1rem 0.75rem;
  }
  
  .stat-number {
    font-size: 1.5rem;
  }
  
  .tab-navigation {
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
  }
  
  .tab-button {
    width: 200px;
    justify-content: center;
  }
  
  .trip-cities,
  .cities-grid {
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 0.5rem;
  }
}

@media (max-width: 480px) {
  .travel-stats {
    grid-template-columns: 1fr;
    max-width: 200px;
  }
  
  .countries-grid,
  .trip-places {
    padding: 1rem;
  }
  
  .country-button {
    padding: 0.75rem 1rem;
  }
  
  .cities-container {
    padding: 1rem;
  }
}

/* Smooth animations - Matches site style */
.hero,
.map-section,
.travels-container {
  animation: fadeInUp 0.6s ease-out;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>

<script>
// Travel data organized by country/region
const travels = {
  'Canada': {
    'British Columbia': [
      'Victoria', 'Vancouver', 'Tofino', 'Nanaimo', 'Whistler', 'Kamloops', 'Kelowna', 'Vernon',
      'Salmon Arm', 'Harrison Hot Springs', 'Williams Lake', 'Quesnel', 'Barkerville',
      'Grand Forks', 'Parksville', 'Duncan', 'Saltspring Island', 'North Pender Island',
      'South Pender Island', 'Galiano', 'Mayne Island', 'Sidney', 'Langford', 'Squamish',
      'Lake Cowichan', 'Merritt', 'Penticton', 'Revelstoke', 'Kimberley', 'Castlegar',
      'Nelson', 'Trail', 'Cranbrook', 'Chase', 'Lake Louise', 'Golden'
    ],
    'Alberta': [
      'Calgary', 'Drumheller', 'Head-Smashed-In Buffalo Jump', 'Medicine Hat', 'Lethbridge'
    ],
    'Saskatchewan': [
      'Moose Jaw', 'Kerrobert', 'Dodsland', 'North Battleford'
    ],
    'New Brunswick': [
      'Saint John', 'Hampton'
    ]
  },
  'United States': ['Seattle', 'Portland', 'Port Angeles', 'Honolulu'],
  'South Korea': ['Seoul', 'Andong', 'Gyeongju', 'Sokcho', 'Gangneung', 'Busan', 'Incheon'],
  'Japan': ['Tokyo'],
  'Cuba': ['Havana'],
  'Mexico': ['Puerto Vallarta'],
  'United Kingdom': ['London', 'Oxford', 'Bath', 'Edinburgh', 'Aberdeen', 'Belfast', 'Lerwick', 'Scalloway'],
  'Ireland': ['Dublin', 'Galway'],
  'France': ['Paris', 'Strasbourg', 'Dunkirk', 'Dieppe', 'Troyes'],
  'Belgium': ['Bruges'],
  'Netherlands': ['Amsterdam', 'Leiden', 'Noordwijk', 'Utrecht'],
  'Germany': ['Berlin', 'Munich', 'Dresden'],
  'Czech Republic': ['Prague', 'Cesky Krumlov'],
  'Austria': ['Vienna', 'Innsbruck'],
  'Slovakia': ['Bratislava'],
  'Slovenia': ['Ljubljana'],
  'Italy': ['Trieste', 'Venice', 'Verona', 'Rome', 'Florence', 'Pisa'],
  'Hungary': ['Budapest'],
  'Croatia': ['Zagreb'],
  'Greece': ['Athens', 'Aegina'],
  'Spain': ['Barcelona', 'Granada', 'Seville', 'Ronda'],
  'Portugal': ['Lisbon', 'Sintra']
};

// Trip data with date ranges
const trips = {
  'Seoul National University Exchange': {
    date: 'Fall 2022',
    description: 'Exchange semester at Seoul National University',
    countries: {
      'South Korea': ['Seoul', 'Andong', 'Gyeongju', 'Sokcho', 'Gangneung', 'Busan', 'Incheon'],
      'Japan': ['Tokyo']
    }
  },
  'Europe Trip 1': {
    date: 'Summer 2019',
    description: 'First major European trip',
    countries: {
      'United Kingdom': ['London', 'Oxford', 'Bath'],
      'France': ['Paris', 'Strasbourg', 'Dunkirk', 'Dieppe', 'Troyes'],
      'Belgium': ['Bruges'],
      'Germany': ['Munich']
    }
  },
  'Post-Graduation Europe Backpacking': {
    date: 'Fall 2023',
    description: 'Three months across as much of Europe as I could get to',
    countries: {
      'Ireland': ['Dublin', 'Galway'],
      'United Kingdom': ['Edinburgh', 'Aberdeen', 'Belfast', 'Lerwick', 'Scalloway'],
      'Netherlands': ['Amsterdam', 'Leiden', 'Noordwijk', 'Utrecht'],
      'Germany': ['Berlin', 'Munich', 'Dresden'],
      'Czech Republic': ['Prague', 'Cesky Krumlov'],
      'Austria': ['Vienna', 'Innsbruck'],
      'Slovakia': ['Bratislava'],
      'Slovenia': ['Ljubljana'],
      'Italy': ['Trieste', 'Venice', 'Verona', 'Rome', 'Florence', 'Pisa'],
      'Hungary': ['Budapest'],
      'Croatia': ['Zagreb'],
      'Greece': ['Athens', 'Aegina'],
      'Spain': ['Barcelona', 'Granada', 'Seville', 'Ronda'],
      'Portugal': ['Lisbon', 'Sintra']
    }
  }
};

const continents = {
  'North America': ['Canada', 'United States', 'Mexico', 'Cuba'],
  'Europe': ['United Kingdom', 'Ireland', 'France', 'Belgium', 'Netherlands', 'Germany', 'Czech Republic', 'Austria', 'Slovakia', 'Slovenia', 'Italy', 'Hungary', 'Croatia', 'Greece', 'Spain', 'Portugal'],
  'Asia': ['South Korea', 'Japan'],
  'Oceania': []
};

// GPS coordinates from the GPX file (cleaned up)
const coordinates = [
  { name: 'Berlin', lat: 52.517048, lon: 13.388881, country: 'Germany' },
  { name: 'Andong', lat: 36.563483, lon: 128.72607, country: 'South Korea' },
  { name: 'Gyeongju', lat: 35.855687, lon: 129.22488, country: 'South Korea' },
  { name: 'Seoul', lat: 37.56668, lon: 126.97829, country: 'South Korea' },
  { name: 'Victoria', lat: 48.428319, lon: -123.36495, country: 'Canada' },
  { name: 'Vancouver', lat: 49.260878, lon: -123.11394, country: 'Canada' },
  { name: 'Seattle', lat: 47.603838, lon: -122.33005, country: 'United States' },
  { name: 'Portland', lat: 45.52026, lon: -122.67419, country: 'United States' },
  { name: 'Calgary', lat: 51.046107, lon: -114.06546, country: 'Canada' },
  { name: 'Kamloops', lat: 50.675839, lon: -120.33942, country: 'Canada' },
  { name: 'Kelowna', lat: 49.887907, lon: -119.49588, country: 'Canada' },
  { name: 'Vernon', lat: 50.266868, lon: -119.27182, country: 'Canada' },
  { name: 'Nanaimo', lat: 49.163877, lon: -123.93813, country: 'Canada' },
  { name: 'Moose Jaw', lat: 50.401506, lon: -105.5429, country: 'Canada' },
  { name: 'Kerrobert', lat: 51.915888, lon: -109.13654, country: 'Canada' },
  { name: 'Saint John', lat: 45.278751, lon: -66.058044, country: 'Canada' },
  { name: 'Havana', lat: 23.135292, lon: -82.358954, country: 'Cuba' },
  { name: 'London', lat: 51.507318, lon: -0.12765171, country: 'United Kingdom' },
  { name: 'Paris', lat: 48.853496, lon: 2.3483923, country: 'France' },
  { name: 'Munich', lat: 48.1371, lon: 11.575364, country: 'Germany' },
  { name: 'Strasbourg', lat: 48.584604, lon: 7.7507052, country: 'France' },
  { name: 'Bruges', lat: 51.208541, lon: 3.2267837, country: 'Belgium' },
  { name: 'Dunkirk', lat: 51.034773, lon: 2.3772314, country: 'France' },
  { name: 'Dieppe', lat: 49.924611, lon: 1.0791279, country: 'France' },
  { name: 'Troyes', lat: 48.297175, lon: 4.0746193, country: 'France' },
  { name: 'Oxford', lat: 51.752026, lon: -1.2578703, country: 'United Kingdom' },
  { name: 'Bath', lat: 51.381388, lon: -2.359679, country: 'United Kingdom' },
  { name: 'Tofino', lat: 49.152964, lon: -125.90471, country: 'Canada' },
  { name: 'Drumheller', lat: 51.466271, lon: -112.70466, country: 'Canada' },
  { name: 'Head-Smashed-In Buffalo Jump', lat: 49.707542, lon: -113.65304, country: 'Canada' },
  { name: 'Dodsland', lat: 51.8, lon: -108.83333, country: 'Canada' },
  { name: 'Medicine Hat', lat: 50.043029, lon: -110.67902, country: 'Canada' },
  { name: 'Golden', lat: 51.298258, lon: -116.96428, country: 'Canada' },
  { name: 'Salmon Arm', lat: 50.700506, lon: -119.27905, country: 'Canada' },
  { name: 'Harrison Hot Springs', lat: 49.299175, lon: -121.78461, country: 'Canada' },
  { name: 'North Battleford', lat: 52.776177, lon: -108.30047, country: 'Canada' },
  { name: 'Hampton', lat: 45.530663, lon: -65.835729, country: 'Canada' },
  { name: 'Williams Lake', lat: 52.129266, lon: -122.13972, country: 'Canada' },
  { name: 'Quesnel', lat: 52.979428, lon: -122.49363, country: 'Canada' },
  { name: 'Barkerville', lat: 53.066669, lon: -121.51667, country: 'Canada' },
  { name: 'Whistler', lat: 50.117189, lon: -122.9543, country: 'Canada' },
  { name: 'Grand Forks', lat: 49.031218, lon: -118.43922, country: 'Canada' },
  { name: 'Parksville', lat: 49.317951, lon: -124.31176, country: 'Canada' },
  { name: 'Duncan', lat: 48.778688, lon: -123.70804, country: 'Canada' },
  { name: 'Saltspring Island', lat: 48.825067, lon: -123.48811, country: 'Canada' },
  { name: 'North Pender Island', lat: 48.778766, lon: -123.28174, country: 'Canada' },
  { name: 'Galiano', lat: 48.884985, lon: -123.35099, country: 'Canada' },
  { name: 'Sokcho', lat: 38.206957, lon: 128.59134, country: 'South Korea' },
  { name: 'Gangneung', lat: 37.752531, lon: 128.87595, country: 'South Korea' },
  { name: 'Busan', lat: 35.179953, lon: 129.07524, country: 'South Korea' },
  { name: 'Incheon', lat: 37.455999, lon: 126.7052, country: 'South Korea' },
  { name: 'Mayne Island', lat: 48.845192, lon: -123.28701, country: 'Canada' },
  { name: 'Chase', lat: 50.819335, lon: -119.68618, country: 'Canada' },
  { name: 'Lake Louise', lat: 51.417847, lon: -116.21667, country: 'Canada' },
  { name: 'South Pender Island', lat: 48.749504, lon: -123.21456, country: 'Canada' },
  { name: 'Sidney', lat: 48.65058, lon: -123.39832, country: 'Canada' },
  { name: 'Langford', lat: 48.449775, lon: -123.50465, country: 'Canada' },
  { name: 'Puerto Vallarta', lat: 20.747505, lon: -105.32789, country: 'Mexico' },
  { name: 'Tokyo', lat: 35.681267, lon: 139.75765, country: 'Japan' },
  { name: 'Lerwick', lat: 60.153136, lon: -1.1427297, country: 'United Kingdom' },
  { name: 'Edinburgh', lat: 55.953349, lon: -3.1883744, country: 'United Kingdom' },
  { name: 'Aberdeen', lat: 57.148247, lon: -2.0927885, country: 'United Kingdom' },
  { name: 'Prague', lat: 50.087466, lon: 14.421252, country: 'Czech Republic' },
  { name: 'Amsterdam', lat: 52.37308, lon: 4.8924525, country: 'Netherlands' },
  { name: 'Leiden', lat: 52.159472, lon: 4.4908982, country: 'Netherlands' },
  { name: 'Noordwijk', lat: 52.24109, lon: 4.4461804, country: 'Netherlands' },
  { name: 'Utrecht', lat: 52.090705, lon: 5.1215822, country: 'Netherlands' },
  { name: 'Cesky Krumlov', lat: 48.810652, lon: 14.315058, country: 'Czech Republic' },
  { name: 'Dublin', lat: 53.34939, lon: -6.2605555, country: 'Ireland' },
  { name: 'Galway', lat: 53.274412, lon: -9.0490612, country: 'Ireland' },
  { name: 'Belfast', lat: 54.596391, lon: -5.9301831, country: 'United Kingdom' },
  { name: 'Scalloway', lat: 60.137137, lon: -1.275271, country: 'United Kingdom' },
  { name: 'Vienna', lat: 48.208363, lon: 16.372485, country: 'Austria' },
  { name: 'Bratislava', lat: 48.1517, lon: 17.109306, country: 'Slovakia' },
  { name: 'Innsbruck', lat: 47.296536, lon: 11.40307, country: 'Austria' },
  { name: 'Dresden', lat: 51.049317, lon: 13.738126, country: 'Germany' },
  { name: 'Verona', lat: 45.438503, lon: 10.992402, country: 'Italy' },
  { name: 'Venice', lat: 45.437178, lon: 12.33458, country: 'Italy' },
  { name: 'Trieste', lat: 45.649648, lon: 13.777265, country: 'Italy' },
  { name: 'Zagreb', lat: 45.813097, lon: 15.97728, country: 'Croatia' },
  { name: 'Budapest', lat: 47.497884, lon: 19.040146, country: 'Hungary' },
  { name: 'Ljubljana', lat: 46.050023, lon: 14.506912, country: 'Slovenia' },
  { name: 'Athens', lat: 37.975551, lon: 23.734827, country: 'Greece' },
  { name: 'Aegina', lat: 37.746703, lon: 23.430626, country: 'Greece' },
  { name: 'Rome', lat: 41.89332, lon: 12.482932, country: 'Italy' },
  { name: 'Florence', lat: 43.769874, lon: 11.255559, country: 'Italy' },
  { name: 'Pisa', lat: 43.715927, lon: 10.401844, country: 'Italy' },
  { name: 'Barcelona', lat: 41.393688, lon: 2.1636562, country: 'Spain' },
  { name: 'Granada', lat: 37.173504, lon: -3.5995464, country: 'Spain' },
  { name: 'Seville', lat: 37.388627, lon: -5.9953387, country: 'Spain' },
  { name: 'Lisbon', lat: 38.707737, lon: -9.1365706, country: 'Portugal' },
  { name: 'Kimberley', lat: 49.685086, lon: -115.98193, country: 'Canada' },
  { name: 'Castlegar', lat: 49.316161, lon: -117.66357, country: 'Canada' },
  { name: 'Nelson', lat: 49.494881, lon: -117.29003, country: 'Canada' },
  { name: 'Trail', lat: 49.094543, lon: -117.70979, country: 'Canada' },
  { name: 'Ronda', lat: 36.742138, lon: -5.1666004, country: 'Spain' },
  { name: 'Port Angeles', lat: 48.118138, lon: -123.43075, country: 'United States' },
  { name: 'Squamish', lat: 49.698079, lon: -123.15587, country: 'Canada' },
  { name: 'Lake Cowichan', lat: 48.825948, lon: -124.05628, country: 'Canada' },
  { name: 'Merritt', lat: 50.112478, lon: -120.78841, country: 'Canada' },
  { name: 'Penticton', lat: 49.500316, lon: -119.59326, country: 'Canada' },
  { name: 'Revelstoke', lat: 50.998056, lon: -118.19567, country: 'Canada' },
  { name: 'Cranbrook', lat: 49.510739, lon: -115.76727, country: 'Canada' },
  { name: 'Lethbridge', lat: 49.694581, lon: -112.8331, country: 'Canada' },
  { name: 'Sintra', lat: 38.798461, lon: -9.3881004, country: 'Portugal' },
  { name: 'Honolulu', lat: 21.304551, lon: -157.85568, country: 'United States' }
];

let map;
let markersLayer;
const expandedCountries = new Set();
let currentTab = 'countries';

// Country colors for map visualization
const countryColors = {
  'Canada': '#FF6B6B',
  'United States': '#4ECDC4',
  'Mexico': '#45B7D1',
  'Cuba': '#96CEB4',
  'United Kingdom': '#FFEAA7',
  'Ireland': '#DDA0DD',
  'France': '#74B9FF',
  'Belgium': '#A29BFE',
  'Netherlands': '#FD79A8',
  'Germany': '#FDCB6E',
  'Czech Republic': '#6C5CE7',
  'Austria': '#E17055',
  'Slovakia': '#00B894',
  'Slovenia': '#00CEC9',
  'Italy': '#FF7675',
  'Hungary': '#F39C12',
  'Croatia': '#3498DB',
  'Greece': '#9B59B6',
  'Spain': '#E74C3C',
  'Portugal': '#F1C40F',
  'South Korea': '#2ECC71',
  'Japan': '#E67E22'
};

function getContinentForCountry(country) {
  for (const [continent, countries] of Object.entries(continents)) {
    if (countries.includes(country)) {
      return continent;
    }
  }
  return 'Other';
}

function showTab(tabName) {
  currentTab = tabName;
  
  // Update tab buttons
  document.querySelectorAll('.tab-button').forEach(btn => {
    btn.classList.remove('active');
  });
  document.querySelector(`[onclick="showTab('${tabName}')"]`).classList.add('active');
  
  // Show/hide tab content
  document.getElementById('trips-tab').style.display = tabName === 'trips' ? 'block' : 'none';
  document.getElementById('countries-tab').style.display = tabName === 'countries' ? 'block' : 'none';
}

function toggleCountry(country) {
  const citiesContainer = document.getElementById(`cities-${country.replace(/\s+/g, '-').replace(/[^a-zA-Z0-9-]/g, '')}`);
  const arrow = document.getElementById(`arrow-${country.replace(/\s+/g, '-').replace(/[^a-zA-Z0-9-]/g, '')}`);
  
  if (expandedCountries.has(country)) {
    expandedCountries.delete(country);
    citiesContainer.classList.remove('expanded');
    arrow.classList.remove('expanded');
  } else {
    expandedCountries.add(country);
    citiesContainer.classList.add('expanded');
    arrow.classList.add('expanded');
  }
}

function initializeMap() {
  if (typeof L === 'undefined') {
    console.error('Leaflet not loaded');
    return;
  }
  
  map = L.map('map').setView([50.0, 10.0], 2);
  
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors'
  }).addTo(map);

  markersLayer = L.layerGroup().addTo(map);
  
  // Add markers for all coordinates
  coordinates.forEach(coord => {
    const color = countryColors[coord.country] || '#333333';
    const marker = L.circleMarker([coord.lat, coord.lon], {
      radius: 6,
      fillColor: color,
      color: '#ffffff',
      weight: 2,
      opacity: 1,
      fillOpacity: 0.8
    }).bindPopup(`<strong>${coord.name}</strong><br>${coord.country}`);
    
    markersLayer.addLayer(marker);
  });
}

function renderTrips() {
  const container = document.getElementById('trips-container');

  container.innerHTML = Object.entries(trips).map(([tripName, tripData]) => `
    <div class="trip-section">
      <div class="trip-header">
        <h3 class="trip-title">
          <i data-feather="map-pin" class="icon"></i>
          ${tripName}
        </h3>
        <div class="trip-date">${tripData.date}</div>
        <div class="trip-summary">${tripData.description}</div>
      </div>
      
      <div class="trip-places">
        ${Object.entries(tripData.countries).map(([country, places]) => `
          <div class="trip-country">
            <div class="trip-country-header">${country} (${places.length} places)</div>
            <div class="trip-cities">
              ${places.map(place => `<div class="city-tag">${place}</div>`).join('')}
            </div>
          </div>
        `).join('')}
      </div>
    </div>
  `).join('');
  
  // Initialize Feather icons for the dynamically added content
  if (typeof feather !== 'undefined') {
    feather.replace();
  }
}

function renderTravelTracker() {
  const container = document.getElementById('continents-container');

  const groupedByContinents = {};
  
  Object.entries(travels).forEach(([country, places]) => {
    const continent = getContinentForCountry(country);
    if (!groupedByContinents[continent]) {
      groupedByContinents[continent] = {};
    }
    groupedByContinents[continent][country] = places;
  });

  container.innerHTML = Object.entries(groupedByContinents).map(([continent, countries]) => `
    <div class="continent-section">
      <div class="continent-header">
        <h3 class="continent-title">
          <i data-feather="map" class="icon"></i>
          ${continent}
          <span class="country-count">(${Object.keys(countries).length} countries)</span>
        </h3>
      </div>
      
      <div class="countries-grid">
        ${Object.entries(countries).map(([country, places]) => {
          const countryId = country.replace(/\s+/g, '-').replace(/[^a-zA-Z0-9-]/g, '');
          
          if (country === 'Canada') {
            const totalCanadianPlaces = Object.values(places).flat().length;
            return `
              <div class="country-item">
                <button class="country-button" onclick="toggleCountry('${country}')">
                  <span class="country-name">${country}</span>
                  <div class="country-info">
                    <span class="place-count">
                      ${totalCanadianPlaces} places across ${Object.keys(places).length} provinces
                    </span>
                    <div class="expand-arrow" id="arrow-${countryId}">▶</div>
                  </div>
                </button>
                
                <div class="cities-container" id="cities-${countryId}">
                  ${Object.entries(places).map(([province, cities]) => `
                    <div class="province-section">
                      <div class="province-header">
                        ${province}
                        <span class="province-count">${cities.length} places</span>
                      </div>
                      <div class="cities-grid">
                        ${cities.map(city => `<div class="city-tag">${city}</div>`).join('')}
                      </div>
                    </div>
                  `).join('')}
                </div>
              </div>
            `;
          } else {
            return `
              <div class="country-item">
                <button class="country-button" onclick="toggleCountry('${country}')">
                  <span class="country-name">${country}</span>
                  <div class="country-info">
                    <span class="place-count">
                      ${places.length} ${places.length === 1 ? 'place' : 'places'}
                    </span>
                    <div class="expand-arrow" id="arrow-${countryId}">▶</div>
                  </div>
                </button>
                
                <div class="cities-container" id="cities-${countryId}">
                  <div class="cities-grid">
                    ${places.map(city => `<div class="city-tag">${city}</div>`).join('')}
                  </div>
                </div>
              </div>
            `;
          }
        }).join('')}
      </div>
    </div>
  `).join('');
  
  // Initialize Feather icons for the dynamically added content
  if (typeof feather !== 'undefined') {
    feather.replace();
  }
}

// Initialize everything when page loads
document.addEventListener('DOMContentLoaded', function() {
  renderTrips();
  renderTravelTracker();
  setTimeout(initializeMap, 100);

  // Set default tab to countries
  showTab('countries');

  // Initialize Feather icons
  if (typeof feather !== 'undefined') {
    feather.replace();
  }
});
</script>
