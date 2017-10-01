From: /Users/richardhoward/bitmaker/lessons/12lesson-sept26/geordis-replicator/episode-06/replicator.rb @ line 112 Replicator#glass_inside_replicator:

    107: def glass_inside_replicator
    108:   # This reaches into the @inside_replicator location instance
    109:   # and then into the `contents` of that instance, which is an array
    110:   # and obtains the first element of that array.
    111:   @inside_replicator.contents.first
 => 112:   binding.pry
    113: end

[1] pry(#<Replicator>)> @inside_replicator.contents.first
=> nil

so something is wrong here
