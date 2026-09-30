
sigfm_sources = ['sigfm.cpp']

# Prefer OpenCV 5 (e.g. Arch Linux ships opencv5.pc), fall back to OpenCV 4
opencv = dependency('opencv5', required: false)
if not opencv.found()
    opencv = dependency('opencv4', required: true)
endif
doctest = dependency('doctest', required: true)

libsigfm = static_library('sigfm',
        sigfm_sources,
        dependencies: [opencv],
)
sigfm_tests = executable('sigfm-tests', ['./tests.cpp'], dependencies: [doctest, opencv], link_with: [libsigfm])
