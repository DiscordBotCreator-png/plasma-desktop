kconfig_add_kcfg_files(emojier_KCFG emojiersettings.kcfgc GENERATE_MOC)

add_executable(ibus-ui-emojier-plasma emojier.cpp resources.qrc ${emojier_KCFG})
target_link_libraries(ibus-ui-emojier-plasma Qt::Widgets GLIB2::GLIB2 PkgConfig::IBUS Qt::Quick Qt::X11Extras KF5::ConfigGui KF5::I18n KF5::CoreAddons KF5::Crash KF5::QuickAddons KF5::DBusAddons KF5::WindowSystem)

install(TARGETS ibus-ui-emojier-plasma ${KDE_INSTALL_TARGETS_DEFAULT_ARGS})
install(FILES org.kde.plasma.emojier.desktop DESTINATION ${KDE_INSTALL_DATADIR}/kglobalaccel)
install(PROGRAMS org.kde.plasma.emojier.desktop DESTINATION ${KDE_INSTALL_APPDIR} )
