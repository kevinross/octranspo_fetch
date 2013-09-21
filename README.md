Wrapper around OC Transpo API
-----------------------------

Example:

    require 'octranspo_fetch'

    oct = OCTranspo.new({application_id: "xxx", application_key: "yyy"})

    trips = oct.simple_get_next_trips_for_stop '0867'
    # Limit to 5 results
    trips = trips[0...5]
    trips.each do |trip|
        puts "Route: #{trip[:route_no]} to #{trip[:destination]} arrives in #{trip[:adjusted_schedule_time]} minutes"
    end