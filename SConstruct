# SConstruct

import os
from osxbundle import TOOL_BUNDLE

def configure_qt():
    qt5_dir = os.environ.get('QT5_DIR', "/usr")

    env = Environment(
        tools=['default', 'qt5'],
        QT5DIR=qt5_dir
    )
    env['QT5_DEBUG'] = 1
    maybe_pkg_config_path = os.environ.get('PKG_CONFIG_PATH')
    if maybe_pkg_config_path:
        env['ENV']['PKG_CONFIG_PATH'] = maybe_pkg_config_path

    env.Append(CCFLAGS=['-fPIC', '-std=c++11'])
    env.EnableQt5Modules(['QtCore', 'QtWidgets', 'QtNetwork'])


    return env

env = configure_qt()
env.Program('application', source=['application.cc'])

bundle_env = Environment()
TOOL_BUNDLE(bundle_env)


bundledir = "the_bundle.app"
app = None
key = "foobar"
info_plist = None
typecode = 'APPL'

bundle_env.MakeBundle(bundledir, app, key, info_plist, typecode=typecode)
