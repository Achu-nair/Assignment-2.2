# Assignment-2.2
assignments for Acadgild Data Science with R course

1.reading multiple JSON file into one data set
answer:

        #load library
        library(rjson)
        #create list
        fname<-- list.files("C:\\Aswathi\\RProgram\\MyWork",pattern= "*.json", full.names=TRUE)
        myjson <-- lapply(fname, function(x) fromJSON(file = x))
  
2. parsing json into dtaframe.

        temp <- list.files(C:\\Aswathi\\RProgram\\MyWork, pattern="*.json", full.names=TRUE)
        movies <- purrr::map_df(temp, function(x) { 
        purrr::map(jsonlite::fromJSON(x), function(y) ifelse(is.null(y), NA, y)) 
        })

3. variable binning using R

        # example of 1-dim use
        x  <- rnorm(1000)
        xb <- binning(x)
        xb <- binning(x, breaks=seq(-4,4,by=0.5))
        
        # example of 2-d use
        x <- rnorm(1000)
        y <- 2*x + 0.5*rnorm(1000)
        x <- cbind(x, y)
        xb<- binning(x, nbins=12)
