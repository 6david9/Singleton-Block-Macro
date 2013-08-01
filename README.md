Singletone-Block-Macro
======================

It's a macro for synthesize the singleton by using dispatch_once. 


	#define SYNTHESIZE_SINGLETONE_FOR_CLASS(CLASS_NAME) \  
	+ (id)sharedInstance \  
	{\  
 	    static CLASS_NAME *__##CLASS_NAME##_instance = nil;\  
	\  
  	    static dispatch_once_t onceToken;\  
   	    dispatch_once(&onceToken, ^{\  
   	       __##CLASS_NAME##_instance = [[CLASS_NAME alloc] init];\  
        });\  
        return __##CLASS_NAME##_instance;\  
	}  

	#define DECLARE_SINGLETON() \  
	+ (id)sharedInstance;  