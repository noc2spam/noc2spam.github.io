definitions[]
   preheader
    type=object
    max_occurs number =1 
    properties
      html
        type=string
    required[]=html
  block
    type=object
    max_occurs number = 0
    properties
      id
        type=string
      block_type
        custom
          max_occurs number = 0
          type=object
          allowed_children[] = #/definitions/block/custom,#/definitions/block/banner,#/definitions/block/1column,#/definitions/block/2column,#/definitions/block/3column,#/definitions/block/navigation
          properties
            id
              type=string
            class
              type=string
            style
              type=string
            html
              type=string
          required[]=html
        list
          type=object
          max_occurs number=0      
          properties
            nazev
              type=string
            popis 
              type=string
            img 
              type=url
            url 
              type=url
            sleva 
              type=float
        banner
          type=object
          max_occurs number = 0
          allowed_children[]
          properties
            img_url
              type=url
            link 
              type=url
            popis 
              type=string
        1column
          type=object
          max_occurs number=0
          allowed_children[]
          properties
            items
              type=object
              max_occurs number=1
              properties
                nazev
                  type=string
                popis
                  type=string
                img
                  type=string
                url
                  type=url
                cena
                  type=float
                orig_cena
                  type=float
                brand
                  type=string
                brand_logo
                  type=url
                brand_url
                  type=url
                novinka
                  type=string
        2column
          type=object
          extends=#/definitions/block/1column
          properties
            items
              max_occurs number=2
        3column
          type=object
          extends=#/definitions/block/1column
          properties
            items
              max_occurs number=3
        navigation
          type=object
          max_occurs number=0
          properties
            id
              type=string
            class
              type=string
            style
              type=string          
            links
              type=object
              max_occurs number = 10
              properties
                id
                  type=string
                class
                  type=string
                style
                  type=string
                name
                  type=string
                url
                  type=url
                target
                  type=string
              required[]=name,url
