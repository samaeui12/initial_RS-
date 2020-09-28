# data_Set

    -- explicit 
        -- item profile data 있냐 / 없냐 
        -- rating 확실한
        
    -- implicit

       -- CTR , binary 값 (구매/ 비구메 ) , 클릭 / 비클릭


    --  memory based

        -- content based
            -- cold start 문제가 없고 

        cf 계열  (latent factor model)
            -- item item 
                안정적이야 (# item> #user)
            -- user user

                -- mf -  R~=<P,Q> P => user latent facor , Q => item latent factor 
                        -- 만약 z R에 포함이 안되어있으면 z는 latent factor 
                        - - 어떻게 추천을 할꺼냐
                        - user가 trained 에 안쓰인 user에 대해 추천할 경우
                          - OLS 
                        - trained에 쓰인 user에 대해 추천할 경우
                 SVD, PMF, PCA
            
    -- hybrid

    -- model based
        -- linear
            -- logistic, FM, FFM
        -- nonlinear
            -- shellow
                -- wide and deep
            -- deep
                -- autoencoder (PCA 일반화 버젼)
                -- deep neural (DeepFM, XdeepFM) 
