# quest

1. <b> Michael is a shop owner who keeps a list of the name and sale price for each item in the store's inventory.
At each sale, his employees record the name and sale price of each item sold. Michael suspects his
manager, Alex, of embezzling money by modifying the sale price of some of the items. Write a program
that finds the number of times Alex recorded an incorrect sale price. </b>
    
allItems = ["rice","sugar","wheat","cheese"] || process.argv[0]
orgPrice=[16,56,20,345] || process.argv[0]
soldItem = ["rice","sugar"] || process.argv[0]
soldPrice=[18,400] || process.argv[0]

function verifyItems(allItems,orgPrice,soldItem,soldPrice){
    let faultySale=0;
    for(let i=0;i<soldItem.length;i++){
        for(let j=0;j<allItems.length;j++){
            if(soldItem[i]==allItems[j]){
                if(soldPrice[i]!=orgPrice[j]){
                    faultySale++;
                }
                break;
            }
        }
    }
    return faultySale;
}

console.info(" test 1 - ",verifyItems(allItems,orgPrice,soldItem,soldPrice))


2.<b> Create an image preview tool that can be used to preview images, with the following preferred methods:
 Drag and Drop: The image is dragged from the computer and dropped on the previewer.
 Image Link: The image link is provided. </b>



<div class="uploader" onclick="$('#filePhoto').click()">
    click here or drag here your images for preview and set userprofile_picture data
<img src=""/>
    <input type="file" name="userprofile_picture"  id="filePhoto" />
    </div>

var imageLoader = document.getElementById('filePhoto');
    imageLoader.addEventListener('change', handleImage, false);

function handleImage(e) {
    var reader = new FileReader();
    reader.onload = function (event) {
        
        document.getElementById("preview").src = event.target.result;
        console.info("url data",document.getElementById("preview").src);
    }
    reader.readAsDataURL(e.target.files[0]);
}


3. <b> Given a string substr, getMovieTitles must perform the following tasks: 
1. Query https://jsonmock.hackerrank.com/api/movies/search/?Title=substr(replace substr). 
2. Initialize the titles array to store total string elements. Store the Title of each movie meeting the search 
criterion in the titles array. 
3. Sort titles in ascending order and return it as your answer. 
The query response from the website is a JSON response with the following five fields: 
• page: The current page. 
• per_page: The maximum number of results per page. 
• total: The total number of movies in the search result. 
• total_pages: The total number of pages which must be queried to get all the results. 
• data: An array of JSON objects containing movie information where the Title field denotes the title of the 
movie. 
In order to get all results, you may have to make multiple page requests. To request a page by number, 
your query should read 
https://jsonmock.hackerrank.com/api/movies/search/?Title=substr&page=pageNumber, replacing substr 
and pageNumber. 
Input Format For Custom Testing 
Input from stdin will be processed as follows and passed to the function. 
A single string, substr, denoting the substring you must query for. 
Sample Case 0 
Sample Input 0 
spiderman 
Sample Output 0 
Amazing Spiderman Syndrome 
Fighting, Flying and Driving: The Stunts of Spiderman 3 
Hollywood's Master Storytellers: Spiderman Live 
Italian Spiderman 
Spiderman 
Spiderman 
Spiderman 5 
Spiderman and Grandma 
Spiderman in Cannes 
Superman, Spiderman or Batman 
The Amazing Spiderman T4 Premiere Special 
The Death of Spiderman 
They Call Me Spiderman 
Explanation 0 
For this example, we want all the movie titles containing the substring spiderman. The response for the 
query https://jsonmock.hackerrank.com/api/movies/search/?Title=spiderman&page=1 is: 
{ 
"page": "1", "per_page": 10, "total": 13, "total_pages": 2, "data": [ 
{ 
"Poster": "https://images-na.ssl-images- amazon.com/images/M/MV5BYjFhN2RjZTctMzA2Ni00NzE2LWJmYjMtNDAyYTllOTkyMmY3XkEyXkFqcG deQXVyNTA0OTU0OTQ@._V1_SX300.jpg", 
"Title": "Italian Spiderman", "Type": "movie", "Year": 2007, "imdbID": "tt2705436" }, { 
"Poster": "https://images-na.ssl-images- amazon.com/images/M/MV5BMjQ4MzcxNDU3N15BMl5BanBnXkFtZTgwOTE1MzMxNzE@._V1_SX300.j pg", 
"Title": "Superman, Spiderman or Batman", "Type": "movie", "Year": 2011, "imdbID": "tt2084949" }, { 
"Poster": "N/A", "Title": "Spiderman", "Type": "movie", "Year": 1990, "imdbID": "tt0100669" }, { 
"Poster": "N/A", "Title": "Spiderman", "Type": "movie", "Year": 2010, "imdbID": "tt1785572" }, { 
"Poster": "N/A", "Title": "Fighting, Flying and Driving: The Stunts of Spiderman 3", "Type": "movie", "Year": 2007, "imdbID": "tt1132238" }, { 
"Poster": "http://ia.media- imdb.com/images/M/MV5BMjE3Mzg0MjAxMl5BMl5BanBnXkFtZTcwNjIyODg5Mg@@._V1_SX300.jpg", 
"Title": "Spiderman and Grandma", "Type": "movie", "Year": 2009, "imdbID": "tt1433184" }, { 
"Poster": "N/A", "Title": "The Amazing Spiderman T4 Premiere Special", "Type": "movie", "Year": 2012, "imdbID": "tt2233044" }, { 
"Poster": "N/A", "Title": "Amazing Spiderman Syndrome", "Type": "movie", 
"Year": 2012, "imdbID": "tt2586634" }, { 
"Poster": "N/A", "Title": "Hollywood's Master Storytellers: Spiderman Live", "Type": "movie", "Year": 2006, "imdbID": "tt2158533" }, { 
"Poster": "N/A", "Title": "Spiderman 5", "Type": "movie", "Year": 2008, "imdbID": "tt3696826" } ] } The response for the query 
https://jsonmock.hackerrank.com/api/movies/search/?Title=spiderman&page=2 is: 
{ 
"page": "2", "per_page": 10, "total": 13, "total_pages": 2, "data": [ 
{ 
"Poster": "N/A", "Title": "They Call Me Spiderman", "Type": "movie", "Year": 2016, "imdbID": "tt5861236" }, { 
"Poster": "N/A", "Title": "The Death of Spiderman", "Type": "movie", "Year": 2015, "imdbID": "tt5921428" }, { 
"Poster": "https://images-na.ssl-images- amazon.com/images/M/MV5BZDlmMGQwYmItNTNmOS00OTNkLTkxNTYtNDM3ZWVlMWUyZDIzXkEy XkFqcGdeQXVyMTA5Mzk5Mw@@._V1_SX300.jpg", 
"Title": "Spiderman in Cannes", 
"Type": "movie", "Year": 2016, "imdbID": "tt5978586" } ] } The values of the Title field for each movie in each response page in the order received are: 
Italian Spiderman 
Superman, Spiderman or Batman 
Spiderman 
Spiderman 
Fighting, Flying and Driving: The Stunts of Spiderman 3 
Spiderman and Grandma 
The Amazing Spiderman T4 Premiere Special 
Amazing Spiderman Syndrome 
Hollywood's Master Storytellers: Spiderman Live 
Spiderman 5 
They Call Me Spiderman 
The Death of Spiderman 
Spiderman in Cannes 
We then sort the array in ascending order, and return it as our answer. </b>


https://github.com/sanwalkailash/MEAN/commit/a62427b7a96437949078ce3b4580ac0ebe9d08ae

async function(req,res)        {
          try {
              console.info("@listMoives...")
              let errors = [];
              if(!req.query.page){
                  req.query.page=1
              }
              if(!req.query.per_page){
                  req.query.per_page=10
              }
              console.info(req.query.page,":",req.query.per_page)
              let movies = await models.moviesSchema
                  .find({"Title":{'$regex': req.query.Title, '$options': 'i'}})
                  .skip((req.query.page-1)*req.query.per_page)
                  .limit(req.query.per_page)
                  .sort({"Title":'asc'})
              let count = await models.moviesSchema.count();

              res.json({
                  "page": req.query.page,
                  "per_page": req.query.per_page,
                  "total": count,
                  "total_pages":Math.ceil(count/req.query.per_page),
                  "data":movies
              })
          }catch(e) {
              console.trace(e);
              res.json({
                  "status": appConstants.failure,
                  "message": e,
                  "errorcode": 500
              });
          }
      }



