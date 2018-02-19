# SConstruct

import os

qt5_dir = os.environ.get('QT5_DIR', "/usr")


env = Environment(
    tools=['default', 'qt5'],
    QT5DIR=qt5_dir
)
env['QT5_DEBUG'] = 1

env.Append(CCFLAGS=['-fPIC'])
env.EnableQt5Modules(['QtCore', 'QtWidgets', 'QtNetwork'])

env.Program('application', source=['application.cc'])
