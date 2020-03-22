project('shell-huds',
		version: '1.0.0')

python = import('python')
python_install = python.find_installation('python3')

sources = []

git = configuration_data()
git.set('version', meson.project_version())
git_source = configure_file(input: 'src' / 'git-hud.in',
							output: 'git-hud',
							configuration: git)
sources += git_source

bat = configuration_data()
bat.set('version', meson.project_version())
bat_source = configure_file(input: 'src' / 'bat-hud.in',
							output: 'bat-hud',
							configuration: bat)
sources += bat_source
sources += 'src' / 'corona'

install_data(sources, install_dir: './bin', install_mode: 'rwxr-xr-x')
