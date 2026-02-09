# engine_web-ifc

Fork/copy of the open-source web-ifc library by That Open Company. A JavaScript/WebAssembly library for reading and writing IFC (Industry Foundation Classes) files at native speeds, targeting both browser and Node.js environments. This is the core IFC parsing engine used by the BIM viewer projects.

## Tech Stack
- C++ (core IFC parser, compiled to WebAssembly via Emscripten)
- TypeScript (API wrapper and schema generator)
- CMake (C++ build system)
- Emscripten (C++ to WASM compiler)
- esbuild (JS/TS bundling)
- Jest (testing)
- Docker (optional build environment)

## Project Structure
- Sources/ - Source code
  - package.json - npm package definition and build scripts
  - src/cpp/ - C++ source code and CMakeLists.txt for the WASM module
  - src/ts/ - TypeScript API wrapper (web-ifc-api.ts, ifc-schema.ts)
  - src/schema-generator/ - IFC schema code generator (IFC2X3, IFC4, IFC4X3 .exp files)
  - examples/ - Usage examples (Node.js, viewer, TypeScript)
  - tests/ - Functional tests, benchmarks, and regression tests
  - Dockerfile - Container-based build
  - tsconfig.json - TypeScript configuration
- Documentations/ - Documentation templates
- SDK/ - Vendor integration documentation

## Build
Requires Node.js v16+, npm v7+, Emscripten v3.1.44+, and CMake v3.18+.
```bash
cd Sources
npm install
npm run setup-env       # Set up Emscripten environment variables
npm run build-release   # Build WASM + JS API (output in dist/)
```
For development: `npm run dev` to launch a local viewer on port 8080. Run tests with `npm test`.
