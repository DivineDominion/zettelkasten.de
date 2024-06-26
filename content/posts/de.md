---
title: Blog Post Archiv
lang: de
canonical: "/posts/"
custom_path: "/de/posts/"
toc: true
---

<%= render '/_search_box.*' %>

<hr>

👉 [**Erste Schritte** mit der Artikelübersicht](/overview/)! 👈

<!-- TODO: create translated overviews
* Beiträge für jedes Jahr: <%= (2013..Date.today.year).to_a.reverse.map { |y| %Q{[#{y}](/posts/#{y}/)} }.join(", ") %>
* [Zettelkasten Live](/live/) vlog series.
-->

<!--TODO: Autorenseiten übersetzen-->
* Beiträge von [Christian](/authors/christian/) und [Sascha](/authors/sascha/).
* **Beiträge [unserer fantastischen Community](/authors/guests/)** -- vielen Dank!
* [Liste aller Schlagworte](/de/posts/tags/).

<hr>

<aside class="note">
<p>Wir haben erst kürzlich angefangen, auch auf Deutsch zu veröffentlichen. Viele Artikel sind derzeit nur <a href="/posts/" hreflang="en">auf Englisch verfügbar</a>.</p>
</aside>

<% partitioned_sorted_posts_by_year().each do |year, months| %>
<section class="posts_group inset-box">
  <header>
    <h2 id="year-<%= year %>"><%= year %></h2>
  </header>
  <div class="allposts posts_list">
    <% months.each do |month, posts| %>
      <% posts.each do |post| %>
        <%= render '/_post-archive.*', :post => post, :month => month, :show_author => true %>
      <% end %>
    <% end %>
  </div>
</section>
<% end %>

