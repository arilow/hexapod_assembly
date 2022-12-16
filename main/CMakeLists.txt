set(BLUETOOTH_SRCS 
        "modules/bluetooth/src/bluetooth.cpp"
        "modules/bluetooth/src/bt_nimble.cpp"
        "modules/bluetooth/src/gatt_svr.cpp"
        "modules/bluetooth/src/misc.cpp"
)

set(HEXAPOD_SRCS
    "modules/hexapod/src/hexapod.cpp"
    "modules/hexapod/src/hexapod_leg.cpp"
    "modules/hexapod/src/pca9685_handler.cpp"
)

idf_component_register(SRCS 
    "hexapod_testing.cpp"
    ${HEXAPOD_SRCS}
    ${BLUETOOTH_SRCS}
    
    INCLUDE_DIRS 
    "modules/bluetooth/includes"
    "modules/hexapod/includes"
)

target_compile_options(${COMPONENT_LIB} PRIVATE "-Wno-format")

