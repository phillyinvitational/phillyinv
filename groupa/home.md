<h1>Group A</h1>
{% assign a1 = site.data.a1 %}
{% assign a2 = site.data.a2 %}
{% assign a3 = site.data.a3 %}
{% assign a4 = site.data.a4 %}

<h2>Standings</h2>
<table style="width:100%">
  <tr>
    <th>Team</th>
    <th>Wins</th>
    <th>Losses</th>
  </tr>
  <tr>
    <td>{{a1.teamname}}</td>
    <td>{{a1.grp_win}}</td>
    <td>{{a1.grp_loss}}</td>
  </tr>
  <tr>
    <td>{{a2.teamname}}</td>
    <td>{{a2.grp_win}}</td>
    <td>{{a2.grp_loss}}</td>
  </tr>
  <tr>
    <td>{{a3.teamname}}</td>
    <td>{{a3.grp_win}}</td>	
    <td>{{a3.grp_loss}}</td>
  </tr>
  <tr>
    <td>{{a4.teamname}}</td>
    <td>{{a4.grp_win}}</td>
    <td>{{a4.grp_loss}}</td>
  </tr>
</table>

<br>

<h2>Schedule</h2>
<table style="width:100%">
  <tr>
    <th>Matchup</th>
    <th>Time</th>
    <th>Map</th>
    <th>Result</th>
    <th>Match Page</th>
  </tr>
  {% for match_hash in site.data.a_matches %}
  {% assign match = match_hash[1] %}
  <tr>
    <td>{{match.home_team}} vs {{match.away_team}}</td>
    <td>{{match.time}}</td>
    <td>{{match.map}}</td>
    {% if match.complete == False %}	
    <td>{{match.home_rounds}}-{{match.away_rounds}}</td>
    {% else %}
    <td> Not Played Yet </td>
    {% endif %}
    <td><a href="/groupa/{{match.id}}">Match Stats</a></td>
  </tr>
  {% endfor %}
 </table>