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

# SCons build file
env = Environment()
# Build the tikz figures and send them to the figures folder
SConscript('tikz/SConscript', variant_dir='figures', duplicate=0)
# Build LaTeX
env.AppendUnique(PDFLATEXFLAGS='-synctex=1')
basename = 'main'
pdf = env.PDF(basename + '.tex')
# Force to build the main pdf when the dependencies changes
dependencies = get_files('tikz')
Depends(pdf, dependencies)
# Make sure that the PDF is reloaded properly
env.Precious(pdf)
# Clean up
env.Clean(pdf, basename + '.synctex.gz')
env.Clean(pdf, 'SConstructc')
env.NoClean(pdf)
