find_package(benchmark REQUIRED)

add_executable(benchmark-multilayer-storage benchmarkMultiLayerStorage.cpp)
target_link_libraries(benchmark-multilayer-storage PRIVATE transaction-scheduler transaction-executor ${EXECUTOR_TARGET} ${LEDGER_TARGET}  ${TARS_PROTOCOL_TARGET} bcos-framework benchmark::benchmark benchmark::benchmark_main)

add_executable(benchmark-scheduler benchmarkScheduler.cpp)
target_link_libraries(benchmark-scheduler PRIVATE transaction-scheduler transaction-executor ${EXECUTOR_TARGET} ${LEDGER_TARGET} ${STORAGE_TARGET} ${TARS_PROTOCOL_TARGET} bcos-framework bcos-crypto benchmark::benchmark benchmark::benchmark_main)