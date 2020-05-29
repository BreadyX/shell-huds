project('shell-huds',
		version: '1.4.0')

repo_url = 'https://github.com/BreadyX/shell-huds.git'

python = import('python')
python_install = python.find_installation('python3')

entries = []
sources = []

if get_option('git_hud').enabled()
  entries += 'git-hud.in'
endif

if get_option('bat_hud').enabled()
  entries += 'bat-hud.in'
endif

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
