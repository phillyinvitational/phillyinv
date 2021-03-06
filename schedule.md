---
title:  Schedule
style:  tabs       # defines body main class
script: standsched
layout: default
datatable: true
---
<h2> Tournament Schedule</h2>
<p>Bolded matchups indicates that it will be streamed at <a href="https://www.twitch.tv/phillyinvitational">PhillyInvitational Twitch</a></p>
<table class="display3">
  <colgroup>
    <col class="thirtyy"/>
    <col class="fifteen"/>
    <col class="fifteen"/>
    <col class="ten"/>
    <col class="fifteen"/>
    <col class="fifteen"/>
  </colgroup>
  <thead>
    <tr>
      <th>Matchup</th>
      <th>Stage</th>
      <th>Time</th>
      <th>Map</th>
      <th>Result</th>
      <th>Match Page</th>
    </tr>
  </thead>
  <tbody>
    {% for match_hash in site.data.a_matches %}
    {% assign match = match_hash[1] %}
    <tr>
      {% if match.home_team == "Silver Surfers" %}
      <td><b>{{match.home_team}} vs {{match.away_team}}</b></td>
      {% else %}
      <td>{{match.home_team}} vs {{match.away_team}}</td>
      {% endif %}
      <td><a href="/groupa/home">Group A</a></td>
      <td>{{match.time}}</td>
      <td>{{match.map}}</td>
      {% if match.complete == "complete" %}	
      <td>{{match.hometag}} {{match.home_rounds}}-{{match.away_rounds}} {{match.awaytag}} </td>
      {% else %}
      <td> Not Played Yet </td>
      {% endif %}
      <td><a href="/groupa/{{match.id}}">Match Stats</a></td>
    </tr>
    {% endfor %}
    {% for match_hash in site.data.b_matches %}
    {% assign match = match_hash[1] %}
    <tr>
      {% if match.home_team == "MotaeSolo" %}
      <td><b>{{match.home_team}} vs {{match.away_team}}</b></td>
      {% else %}
      <td>{{match.home_team}} vs {{match.away_team}}</td>
      {% endif %}
      <td><a href="/groupb/home">Group B</a></td>
      <td>{{match.time}}</td>
      <td>{{match.map}}</td>
      {% if match.complete == "complete" %} 
      <td>{{match.hometag}} {{match.home_rounds}}-{{match.away_rounds}} {{match.awaytag}} </td>
      {% else %}
      <td> Not Played Yet </td>
      {% endif %}
      <td><a href="/groupb/{{match.id}}">Match Stats</a></td>
    </tr>
    {% endfor %}
    {% assign qf1 = site.data.playoff_matches.qf1_1 %}
    <tr>
      <td>{{qf1.home_team}} vs {{qf1.away_team}}</td>
      <td><a href="/playoffs">Quarterfinal 1</a></td>
      <td>{{qf1.time}}</td>
      <td>{{qf1.map}}</td>
      <td>TFN 2-0 MTS</td>
      <td><a href="/playoffs/qf1">Series Stats</a></td>
    </tr>
    {% assign qf2 = site.data.playoff_matches.qf2_1 %}
    <tr>
      <td><b>{{qf2.home_team}} vs {{qf2.away_team}}</b></td>
      <td><a href="/playoffs">Quarterfinal 2</a></td>
      <td>{{qf2.time}}</td>
      <td>{{qf2.map}}</td>
      <td>B9G 0-2 GE</td>
      <td><a href="/playoffs/qf2">Series Stats</a></td>
    </tr>
    {% assign qf3 = site.data.playoff_matches.qf3_1 %}
    <tr>
      <td>{{qf3.home_team}} vs {{qf3.away_team}}</td>
      <td><a href="/playoffs">Quarterfinal 3</a></td>
      <td>{{qf3.time}}</td>
      <td>{{qf3.map}}</td>
      <td>PRVI 2-0 RCB</td>
      <td><a href="/playoffs/qf3">Series Stats</a></td>
    </tr>
    {% assign qf4 = site.data.playoff_matches.qf4_1 %}
    <tr>
      <td>{{qf4.home_team}} vs {{qf4.away_team}}</td>
      <td><a href="/playoffs">Quarterfinal 4</a></td>
      <td>{{qf4.time}}</td>
      <td>{{qf4.map}}</td>
      <td>SUS 2-0 CUD</td>
      <td><a href="/playoffs/qf4">Series Stats</a></td>
    </tr>
    {% assign sf1 = site.data.playoff_matches.sf1_1 %}
    <tr>
      <td>{{sf1.home_team}} vs {{sf1.away_team}}</td>
      <td><a href="/playoffs">Semifinal 1</a></td>
      <td>{{sf1.time}}</td>
      <td>{{sf1.map}}</td>
      <td>PRVI 1-2 SUS</td>
      <td><a href="/playoffs/sf1">Series Stats</a></td>
    </tr>
    {% assign sf2 = site.data.playoff_matches.sf2_1 %}
    <tr>
      <td>{{sf2.home_team}} vs {{sf2.away_team}}</td>
      <td><a href="/playoffs">Semifinal 2</a></td>
      <td>{{sf2.time}}</td>
      <td>{{sf2.map}}</td>
      <td>TFN 2-0 GE</td>
      <td><a href="/playoffs/sf2">Series Stats</a></td>
    </tr>
    {% assign gf = site.data.playoff_matches.gf1_1 %}
    <tr>
      <td>{{gf.home_team}} vs {{gf.away_team}}</td>
      <td><a href="/playoffs">Grand Finals</a></td>
      <td>{{gf.time}}</td>
      <td>{{gf.map}}</td>
      <td>TFN 1-2 SUS</td>
      <td><a href="/playoffs/gf">Series Stats</a></td>
    </tr>
  </tbody>
 </table>