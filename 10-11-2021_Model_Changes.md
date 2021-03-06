#Existing Model changes:

```c#
public class LMSBootcamp
    {
        /// <summary>
        /// Automated area
        /// </summary>
        public bool Automated { get; set; }
    }
```

```c# 
public class LMSCourse
    {
        ///// <summary>
        ///// determines whether it's an Automated Course 
        ///// </summary>
        [Display(Name = "Automated Course")]
        public bool IsAutomated { get; set; }
    }
```

```c#
public class LMSTestQuestion
    {
        [Display(Name = "Wrong String 4")]
        public string WrongString4 { get; set; }


        [Display(Name = "Wrong String 5")]
        public string WrongString5 { get; set; }


        [Display(Name = "Wrong String 6")]
        public string WrongString6 { get; set; }


        [Display(Name = "Wrong String 7")]
        public string WrongString7 { get; set; }


        [Display(Name = "Wrong String 8")]
        public string WrongString8 { get; set; }


        [Display(Name = "Wrong String 9")]
        public string WrongString9 { get; set; }

        ##REMOVE ESSAY
        public string Essay { get; set; }
    }
```    

```c#
public class ApplicationUser
    {
        public bool DarkMode { get; set; }
    }
```    
    
#New Models

```c#
public class AutomatedCurrentCourse
    {
        /// <summary>
        /// Primary Key and Foreign Key to Users table
        /// </summary>
        [Key]
        public string Id { get; set; }


        /// <summary>
        /// Foreign key to relate to the LMSBootCamp table
        /// </summary>
        public int BootCampId { get; set; }


        /// <summary>
        /// Foreign key to relate to the LMSCourse table
        /// </summary>
        public int CourseId { get; set; }


        public int CoursePosition { get; set; }


        public int LastViewedCourseId { get; set; }


        public int? PageNumber { get; set; }


	/// <summary>
	/// Foreign key to relate to the LMSPage table
	/// </summary>
	public int PageId { get; set; }


	public bool ProgressWarningMessage { get; set; }


	public bool CourseProgressBar { get; set; }


	public bool CampProgressBar { get; set; }


	public bool FailedAssignmentLock { get; set; }


        public DateTime LastActive { get; set; }
    }
```  
  
```c#
public class AutomatedRegistrationCurrentCourse
    {
        /// <summary>
?? ?? ?? ?? /// Foreign Key relating to students
?? ?? ?? ?? /// </summary>
?? ?? ?? ?? [Key]
        public string Id { get; set; }

?? ?? ?? ?? /// <summary>
?? ?? ?? ?? /// Foreign Key relating to the bootcamp table 
?? ?? ?? ?? /// </summary>
?? ?? ?? ?? public int BootcampId { get; set; }

?? ?? ?? ?? /// <summary>
?? ?? ?? ?? /// Foreign Key relating to the courses table 
?? ?? ?? ?? /// </summary>
?? ?? ?? ?? public int CourseId { get; set; }

        [Display(Name = "Course Position")]
        public int CoursePosition { get; set; }

?? ?? ?? ?? /// <summary>
?? ?? ?? ?? /// Current page the student is working on
?? ?? ?? ?? /// </summary>
?? ?? ?? ?? [Display(Name = "Page Number")]
        public int? PageNumber { get; set; }

        [Display(Name = "Page Id")]
        public int PageId { get; set; }

        public AutomatedRegistrationCurrentCourse()
        {
        }
    }
```

```c#    
public class DiscussionThread
    {
        /// <summary>
        /// Primary Key
        /// </summary>
        [Key]
        public int DisscussionThreadId { get; set; }


        /// <summary>
        /// Foreign key to relate to LMSCourse Id
        /// </summary>
        public int CourseId { get; set; }


        /// <summary>
        /// Foreign key to relate to user
        /// </summary>
        public int AuthorId { get; set; }


        public bool IsResolved { get; set; }


        public bool IsApproved { get; set; }


        public string Topic { get; set; }


        public string Content { get; set; }


        public DateTime Submitted { get; set; }
        
        
        public bool IsArchived { get; set; }
    }
```

```c# 
public class DiscussionReply
    {
        /// <summary>
        /// Primary Key
        /// </summary>
        [Key]
        public int DiscussionReplyId { get; set; }


        /// <summary>
        /// Foreign key to relate to DiscussionThread Id
        /// </summary>
        public int DiscussionThreadId { get; set; }


        /// <summary>
        /// Foreign key to relate to users
        /// </summary>
        public int AuthorId { get; set; }


        public bool IsApproved { get; set; }


        public int UpVotes { get; set; }


        public string Content { get; set; }


        public DateTime Submitted { get; set; }
    }
```