# 네이버 시리즈 크롤링 계획
- 전체 페이지 -> 3072 페이지에 각각 25개씩 있음 -> 단순 request
	- detail_url 만 가져오면 됨, 작품 id도 가져오면 좋음
- 상세 페이지 -> 총 76789개 작품 존재, selenium 사용해야할 것 같음 thread도 쓰면 좋을듯
	- 제목, 평점, 작가, 출판사, 이용가, 좋아요 수, createCommentBox()에서 sObjectId 꺼내와야함 -> 댓글 수는 못 가져옴
- 댓글 API -> 한 작품 당 몇 개의 댓글을 가져와야할 지?
	- 댓글, 댓글 공감, 비공감

dict 정보
- product
- productNo : string
    - title(제목) : string
    - star_score(별점) : float
    - liked(좋아요) : int
    - author(작가) : string
    - publisher(출판사) : string
    - age_rating(이용등급) : string
    - sObjectId(그냥 넣어본 값) : string
    - comment_list(댓글 리스트) : list
- comment_list
    - contents(실제 댓글) : string
    - sympathyCount(공감) : int
    - antipathyCount(비공감) : int