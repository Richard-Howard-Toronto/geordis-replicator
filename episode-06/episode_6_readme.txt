# This transports a glass from the cupboard to inside the replicator.
# If this method is successful, it will return the glass that was
# transported and @inside_replicator will contain the glass
# in its contents.

this is not happening

    @glass = @inside_replicator.contents.first

    @glass = nil
    @inside_replicator - contents = nil.


IF IT WORKED CORRECTLY IT WOULD return

    [1] pry(#<Replicator>)> @glass
    => #<Glass:0x007f9724072c00
     @errors=[],
     @inside=#<Location:0x007f9724072bd8 @contents=[]>,
     @temperature=37>


So let us look at the method: retrieve_glass

Here it is:

# This moves the glass from the cupboard to inside the replicator.
def retrieve_glass
  @enterprise.transporter.energize(
    @enterprise.cupboard.find_glass,
    @enterprise.cupboard.shelf,
    @inside_replicator
  )
end


cupboard.find_glass

[1] pry(#<Cupboard>)> @shelf
=> #<Location:0x007fd0f3021f40
 @contents=
  [#<Glass:0x007fd0f3021c98
    @errors=[],
    @inside=#<Location:0x007fd0f3021b80 @contents=[]>,
    @temperature=37>,
   #<Glass:0x007fd0f3021a18
    @errors=[],
    @inside=#<Location:0x007fd0f30219c8 @contents=[]>,
    @temperature=37>,
   #<Glass:0x007fd0f3021810
    @errors=[],
    @inside=#<Location:0x007fd0f30217c0 @contents=[]>,
    @temperature=37>,
   #<Glass:0x007fd0f30216d0
    @errors=[],
    @inside=#<Location:0x007fd0f3021608 @contents=[]>,
    @temperature=37>,
   #<Glass:0x007fd0f30213d8
    @errors=[],
    @inside=#<Location:0x007fd0f3021310 @contents=[]>,
    @temperature=37>]>
[2] pry(#<Cupboard>)>


[2] pry(#<Cupboard>)> stock_shelf
=> 5
[3] pry(#<Cupboard>)>

[1] pry(#<Cupboard>)> @shelf.contents
=> [#<Glass:0x007f9ad693bef8
  @errors=[],
  @inside=#<Location:0x007f9ad693bea8 @contents=[]>,
  @temperature=37>]
[2] pry(#<Cupboard>)>
