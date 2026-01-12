# Instructions
- For each event listed in find_new_events/events_to_deploy.json, select the correct configuration file based on the asset type:
  - Use metric_config/config_post_decision_token_price.py for token assets.
  - Use metric_config/config_post_decision_equity_price.py for equity assets.
- Add the event to the respective configuration file, unless an equivalent event is already present.
- Create one config entry for each (event,token) pair. i.e. do not group multiple tokens into the same config event, even if they share the same condition/event.
- Follow the formatting rules at the top of the selected config file and those specified below: 

- Follow the shared guidelines, including the required outcome-forecast CLI workflow and `report_gen_inputs.outcomes` format.

- Ensure no \u unicode escape codes are included in any fields (unicode chars are fine though)

- See: shared_guidelines.md to determine how to format entries in the destination configuration files

- Move all text from find_new_events/events_to_deploy.json and append it to metric_config/new_events_OLD.md, once you have finished