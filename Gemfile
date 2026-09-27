# Нужен только для локального предпросмотра: bundle install && bundle exec jekyll serve
# GitHub Pages собирает сайт сам и этот файл игнорирует. Гем github-pages фиксирует
# ровно те версии Jekyll и плагинов, что работают на стороне GitHub, — поэтому локальная
# сборка совпадает с опубликованной.
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins

# Локальный предпросмотр на Ruby 3.x: Jekyll 3 из github-pages ещё рассчитывает на webrick из
# стандартной библиотеки, а его там больше нет. На Windows вдобавок нет базы часовых поясов.
gem "webrick"
gem "tzinfo-data", platforms: :windows
