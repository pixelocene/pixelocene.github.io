.PHONY: cleanup bs-icons dev prod

cleanup:
	@rm -rf static/css/*.css static/css/*.map
	@rm -rf static/js/*.js
	@rm -rf static/fonts/fonts
	@rm -rf static/font/bootstrap-icons.css

bs-icons:
	cp -r node_modules/bootstrap-icons/font/fonts static/fonts/fonts
	cp node_modules/bootstrap-icons/font/bootstrap-icons.min.css static/fonts/bootstrap-icons.css

dev: cleanup bs-icons
	cp node_modules/bootstrap/dist/js/bootstrap.bundle.js static/js/bootstrap.js
	node_modules/.bin/sass --watch --update --style=expanded assets/scss:static/css

prod: cleanup bs-icons
	cp node_modules/bootstrap/dist/js/bootstrap.bundle.min.js static/js/bootstrap.js
	node_modules/.bin/sass --no-source-map --style=compressed assets/scss:static/css