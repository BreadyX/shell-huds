project('shell-huds',
		version: '1.2.2')

repo_url = 'https://github.com/BreadyX/shell-huds.git'

python = import('python')
python_install = python.find_installation('python3')

entries = ['git-hud.in', 'bat-hud.in', 'corona.in']
sources = []

foreach p : entries
  conf = configuration_data()
  conf.set('version', meson.project_version())
  conf.set('repo_url', repo_url)
  source = configure_file(input: 'src' / p,
						  output: p.split('.')[0],
						  configuration: conf)
  sources += source
endforeach

install_data(sources, install_dir: './bin', install_mode: 'rwxr-xr-x')
