# SCons build file
import os

def get_files(directory):
  file_paths = []
  # Walk the tree.
  for root, directories, files in os.walk(directory):
    for filename in files:
      # Join the two strings in order to form the full filepath.
      filepath = os.path.join(root, filename)
      file_paths.append(filepath)  # Add it to the list.
  return file_paths

env = Environment()

# Build all the figures in the tikz folder and send them to the figures folder
#~ SConscript('tikz/SConscript', variant_dir='figures', duplicate=0)

# Enable SyncTeX.
env.AppendUnique(PDFLATEXFLAGS='-synctex=1')

basename = 'main'
pdf = env.PDF(basename + '.tex')
# Force to build when any file changes
dependencies = get_files('figures') + get_files('scripts') #+ ['references.bib']
Depends(pdf, dependencies)
# make sure that the pdf is reloaded properly
env.Precious(pdf)
# Clean up
env.Clean(pdf, basename + '.synctex.gz')
env.Clean(pdf, 'SConstructc')
env.NoClean(pdf)
