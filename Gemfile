source "https://rubygems.org"

# Inizia con il tema di base
gem "minima", "~> 2.5"

# Il generatore di siti statici Jekyll
gem "jekyll", "~> 4.2.0"

# Plugin Jekyll
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-seo-tag", "~> 2.7"
end

# Aggiungi le gemme necessarie per Ruby 3.4+
gem "csv"
gem "base64"
gem "bigdecimal"
gem "logger"
gem "webrick"  # WebRick è necessario per il server di sviluppo

# Windows e JRuby non includono zoneinfo files, quindi aggiungi la gem tzinfo-data
# e le gems di dipendenze associate
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# Per Performance e congruenza quando si esegue su Windows
# può essere necessario installare le gem eventmachine e wdm
gem "eventmachine", "~> 1.2.7", :platforms => [:mingw, :x64_mingw, :mswin]
gem "wdm", "~> 0.2.0", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds as newer versions require
# Ruby >= 2.0
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]

# Per la compatibilità con GitHub Pages
# gem "github-pages", group: :jekyll_plugins