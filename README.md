⚠️ 🔐 IMPORTANT (Do NOT include these)

❌ Never add:

login.php
register.php
reset_password.php
dashboard.php
admin pages

👉 Sitemap = only public pages

🧠 What each tag means
<loc> → page URL
<lastmod> → last update date
<changefreq> → how often content changes
<priority> → importance (0.0 – 1.0)
📁 2. Where to place it

Save as:

/public_html/sitemap.xml

👉 So it becomes:

https://yourdomain.com/sitemap.xml
🤖 3. Link it in robots.txt

Create or edit robots.txt:

User-agent: *
Allow: /

Sitemap: https://yourdomain.com/sitemap.xml
🚀 4. Submit to search engines

Use:

Google Search Console
Bing Webmaster Tools

👉 Submit:

https://yourdomain.com/sitemap.xml
🔥 BONUS: Dynamic Sitemap (Auto-update)

If your site has many pages (e.g. blog/posts), use PHP:

<?php
header("Content-Type: application/xml; charset=utf-8");

echo '<?xml version="1.0" encoding="UTF-8"?>';
?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

<?php
$conn = new mysqli("localhost", "user", "pass", "db");

$result = $conn->query("SELECT slug, updated_at FROM posts");

while($row = $result->fetch_assoc()) {
    echo "<url>";
    echo "<loc>https://yourdomain.com/post.php?slug=".$row['slug']."</loc>";
    echo "<lastmod>".$row['updated_at']."</lastmod>";
    echo "<changefreq>weekly</changefreq>";
    echo "<priority>0.8</priority>";
    echo "</url>";
}
?>

</urlset>

👉 Save as sitemap.php and link it like:

Sitemap: https://yourdomain.com/sitemap.php
✅ Final Checklist

✔ Only public pages included
✔ No blocked pages inside sitemap
✔ Proper domain URLs
✔ robots.txt linked
✔ Submitted to search engines
