
foreach (_script
    copy_quicklooks
    create_quicklook_tasks
    run_tasks
    )

  ## Installation instructions
  install (FILES ${_script}
    DESTINATION bin
    PERMISSIONS OWNER_EXECUTE OWNER_READ OWNER_WRITE GROUP_EXECUTE GROUP_READ
    )

endforeach (_script)
