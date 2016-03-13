# SCons build file
env = Environment()
# Enable SyncTeX.
env.AppendUnique(PDFLATEXFLAGS='-synctex=1')

basename = 'main'
pdf = env.PDF(basename + '.tex')
# make sure that the pdf is reloaded properly
env.Precious(pdf)
# Clean up
env.Clean(pdf, basename + '.synctex.gz')
env.Clean(pdf, 'SConstructc')
env.NoClean(pdf)
