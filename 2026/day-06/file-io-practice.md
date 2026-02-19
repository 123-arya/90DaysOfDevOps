touch notes.txt
echo "this is linux fundamentals" > notes.txt
echo "this is linux advance" >> notes.txt
echo "this is networking fundamental" | tee -a notes.txt
cat notes.txt
head -n 2 notes.txt
tail -n 2 notes.txt

