#chain consensus module CmakeLists.txt -- libchain_consensus.a

set(LIB_CHAIN_CONSENSUS chain_consensus)
#Automatically get src files from the specified directory
aux_source_directory(${CHAIN_SRC_DIR}/consensus/ CONSENSUS_SRC)

#Generate static library files
add_library(${LIB_CHAIN_CONSENSUS} ${CONSENSUS_SRC})

#Specify compiling options for target objects
target_compile_options(${LIB_CHAIN_CONSENSUS}
    PUBLIC -std=c++11 
    PUBLIC -DASIO_STANDALONE
    PUBLIC -D_WEBSOCKETPP_CPP11_STL_
    PUBLIC -D${OS_NAME}
)

