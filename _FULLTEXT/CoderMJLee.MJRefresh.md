MJRefresh An easy way to use pull-to-refresh Contents Getting Started Features【Support what kinds of controls to refresh】 Installation【How to use MJRefresh】 Whos using【More than hundreds of Apps are using MJRefresh】 Classes【The Class Structure Chart of MJRefresh】 Comment API MJRefreshComponent.h MJRefreshHeader.h MJRefreshFooter.h MJRefreshAutoFooter.h Examples Reference The drop-down refresh 01-Default The drop-down refresh 02-Animation image The drop-down refresh 03-Hide the time The drop-down refresh 04-Hide status and time The drop-down refresh 05-DIY title The drop-down refresh 06-DIY the control of refresh The pull to refresh 01-Default The pull to refresh 02-Animation image The pull to refresh 03-Hide the title of refresh status The pull to refresh 04-All loaded The pull to refresh 05-DIY title The pull to refresh 06-Hidden After loaded The pull to refresh 07-Automatic back of the pull01 The pull to refresh 08-Automatic back of the pull02 The pull to refresh 09-DIY the control of refresh(Automatic refresh) The pull to refresh 10-DIY the control of refresh(Automatic back) UICollectionView01-The pull and drop-down refresh UIWebView01-The drop-down refresh Hope Support what kinds of controls to refresh UIScrollView、UITableView、UICollectionView、UIWebView How to use MJRefresh Installation with CocoaPods：pod MJRefresh Manual import： Drag All files in the MJRefresh folder to project Import the main file：#import "MJRefresh.h" objc Base Custom MJRefresh.bundle MJRefresh.h MJRefreshConst.h MJRefreshConst.m UIScrollView+MJExtension.h UIScrollView+MJExtension.m UIScrollView+MJRefresh.h UIScrollView+MJRefresh.m UIView+MJExtension.h UIView+MJExtension.m More than hundreds of Apps are using MJRefresh * More information of App can focus on：M了个J-博客园 The Class Structure Chart of MJRefresh - The class of red text in the chart：You can use them directly - The drop-down refresh control types - Normal：MJRefreshNormalHeader - Gif：MJRefreshGifHeader - The pull to refresh control types - Auto refresh - Normal：MJRefreshAutoNormalFooter - Gif：MJRefreshAutoGifFooter - Auto Back - Normal：MJRefreshBackNormalFooter - Gif：MJRefreshBackGifFooter - The class of non-red text in the chart：For inheritance，to use DIY the control of refresh - About how to DIY the control of refresh，You can refer the Class in below Chart MJRefreshComponent.h ```objc /* The Base Class of refresh control / @interface MJRefreshComponent : UIView pragma mark - Control the state of Refresh / BeginRefreshing */ - (void)beginRefreshing; / EndRefreshing / - (void)endRefreshing; / IsRefreshing / - (BOOL)isRefreshing; pragma mark - Other /* According to the drag ratio to change alpha automatically / @property (assign, nonatomic, getter=isAutomaticallyChangeAlpha) BOOL automaticallyChangeAlpha; @end ``` MJRefreshHeader.h ```objc @interface MJRefreshHeader : MJRefreshComponent / Creat header */ + (instancetype)headerWithRefreshingBlock:(MJRefreshComponentRefreshingBlock)refreshingBlock; / Creat header */ + (instancetype)headerWithRefreshingTarget:(id)target refreshingAction:(SEL)action; / This key is used to storage the time that the last time of drown-down successfully / @property (copy, nonatomic) NSString lastUpdatedTimeKey; / The last time of drown-down successfully / @property (strong, nonatomic, readonly) NSDate lastUpdatedTime; /* Ignored scrollView contentInset top / @property (assign, nonatomic) CGFloat ignoredScrollViewContentInsetTop; @end ``` MJRefreshFooter.h ```objc @interface MJRefreshFooter : MJRefreshComponent / Creat footer */ + (instancetype)footerWithRefreshingBlock:(MJRefreshComponentRefreshingBlock)refreshingBlock; / Creat footer */ + (instancetype)footerWithRefreshingTarget:(id)target refreshingAction:(SEL)action; / NoticeNoMoreData */ - (void)noticeNoMoreData; / ResetNoMoreData（Clear the status of NoMoreData ） */ - (void)resetNoMoreData; /* Ignored scrollView contentInset bottom / @property (assign, nonatomic) CGFloat ignoredScrollViewContentInsetBottom; /* Automaticlly show or hidden by the count of data（Show-have data，Hidden- no data） / @property (assign, nonatomic) BOOL automaticallyHidden; @end ``` MJRefreshAutoFooter.h ```objc @interface MJRefreshAutoFooter : MJRefreshFooter /* Is Automatically Refresh(Default is Yes) / @property (assign, nonatomic, getter=isAutomaticallyRefresh) BOOL automaticallyRefresh; /* When there is much at the bottom of the control is automatically refresh(Default is 1.0，Is at the bottom of the control appears in full, will refresh automatically) / @property (assign, nonatomic) CGFloat triggerAutomaticallyRefreshPercent; @end ``` Reference objc * Due to there are more functions of this framework，Dont write specific text describe its usage * You can directly reference examples MJTableViewController、MJCollectionViewController、MJWebViewController，More intuitive and fast. The drop-down refresh 01-Default ```objc self.tableView.header = [MJRefreshNormalHeader headerWithRefreshingBlock:^{ //Call this Block When enter the refresh status automatically }]; 或 // Set the callback（Once you enter the refresh status，then call the action of target，that is call [self loadNewData]） self.tableView.header = [MJRefreshNormalHeader headerWithRefreshingTarget:self refreshingAction:@selector(loadNewData)]; // Enter the refresh status immediately [self.tableView.header beginRefreshing]; ``` The drop-down refresh 02-Animation image objc // Set the callback（一Once you enter the refresh status，then call the action of target，that is call [self loadNewData]） MJRefreshGifHeader *header = [MJRefreshGifHeader headerWithRefreshingTarget:self refreshingAction:@selector(loadNewData)]; // Set the ordinary state of animated images [header setImages:idleImages forState:MJRefreshStateIdle]; // Set the pulling state of animated images（Enter the status of refreshing as soon as loosen） [header setImages:pullingImages forState:MJRefreshStatePulling]; // Set the refreshing state of animated images [header setImages:refreshingImages forState:MJRefreshStateRefreshing]; // Set header self.tableView.mj_header = header; The drop-down refresh 03-Hide the time objc // Hide the time header.lastUpdatedTimeLabel.hidden = YES; The drop-down refresh 04-Hide status and time ```objc // Hide the time header.lastUpdatedTimeLabel.hidden = YES; // Hide the status header.stateLabel.hidden = YES; ``` The drop-down refresh 05-DIY title ```objc // Set title [header setTitle:@"Pull down to refresh" forState:MJRefreshStateIdle]; [header setTitle:@"Release to refresh" forState:MJRefreshStatePulling]; [header setTitle:@"Loading ..." forState:MJRefreshStateRefreshing]; // Set font header.stateLabel.font = [UIFont systemFontOfSize:15]; header.lastUpdatedTimeLabel.font = [UIFont systemFontOfSize:14]; // Set textColor header.stateLabel.textColor = [UIColor redColor]; header.lastUpdatedTimeLabel.textColor = [UIColor blueColor]; ``` The drop-down refresh 06-DIY the control of refresh objc self.tableView.mj_header = [MJDIYHeader headerWithRefreshingTarget:self refreshingAction:@selector(loadNewData)]; // Implementation reference to MJDIYHeader.h和MJDIYHeader.m The pull to refresh 01-Default objc self.tableView.mj_footer = [MJRefreshAutoNormalFooter footerWithRefreshingBlock:^{ //Call this Block When enter the refresh status automatically }]; 或 // Set the callback（Once you enter the refresh status，then call the action of target，that is call [self loadMoreData]） self.tableView.mj_footer = [MJRefreshAutoNormalFooter footerWithRefreshingTarget:self refreshingAction:@selector(loadMoreData)]; The pull to refresh 02-Animation image ```objc // Set the callback（Once you enter the refresh status，then call the action of target，that is call [self loadMoreData]） MJRefreshAutoGifFooter *footer = [MJRefreshAutoGifFooter footerWithRefreshingTarget:self refreshingAction:@selector(loadMoreData)]; // Set the refresh image [footer setImages:refreshingImages forState:MJRefreshStateRefreshing]; // Set footer self.tableView.mj_footer = footer; ``` The pull to refresh 03-Hide the title of refresh status objc // Hide the title of refresh status footer.refreshingTitleHidden = YES; // If does have not above method，then use footer.stateLabel.hidden = YES; The pull to refresh 04-All loaded objc //Become the status of NoMoreData [footer noticeNoMoreData]; The pull to refresh 05-DIY title ```objc // Set title [footer setTitle:@"Click or drag up to refresh" forState:MJRefreshStateIdle]; [footer setTitle:@"Loading more ..." forState:MJRefreshStateRefreshing]; [footer setTitle:@"No more data" forState:MJRefreshStateNoMoreData]; // Set font footer.stateLabel.font = [UIFont systemFontOfSize:17]; // Set textColor footer.stateLabel.textColor = [UIColor blueColor]; ``` The pull to refresh 06-Hidden After loaded objc //Hidden current control of the pull to refresh self.tableView.mj_footer.hidden = YES; The pull to refresh 07-Automatic back of the pull01 objc self.tableView.mj_footer = [MJRefreshBackNormalFooter footerWithRefreshingTarget:self refreshingAction:@selector(loadMoreData)]; The pull to refresh 08-Automatic back of the pull02 ```objc MJRefreshBackGifFooter *footer = [MJRefreshBackGifFooter footerWithRefreshingTarget:self refreshingAction:@selector(loadMoreData)]; // Set the normal state of the animated image [footer setImages:idleImages forState:MJRefreshStateIdle]; // Set the pulling state of animated images（Enter the status of refreshing as soon as loosen） [footer setImages:pullingImages forState:MJRefreshStatePulling]; // Set the refreshing state of animated images [footer setImages:refreshingImages forState:MJRefreshStateRefreshing]; // Set footer self.tableView.mj_footer = footer; ``` The pull to refresh 09-DIY the control of refresh(Automatic refresh) objc self.tableView.mj_footer = [MJDIYAutoFooter footerWithRefreshingTarget:self refreshingAction:@selector(loadMoreData)]; // Implementation reference to MJDIYAutoFooter.h和MJDIYAutoFooter.m The pull to refresh 10-DIY the control of refresh(Automatic back) objc self.tableView.mj_footer = [MJDIYBackFooter footerWithRefreshingTarget:self refreshingAction:@selector(loadMoreData)]; // Implementation reference to MJDIYBackFooter.h和MJDIYBackFooter.m UICollectionView01-The pull and drop-down refresh ```objc // The drop-down refresh self.collectionView.mj_header = [MJRefreshNormalHeader headerWithRefreshingBlock:^{ //Call this Block When enter the refresh status automatically }]; // The pull to refresh self.collectionView.mj_footer = [MJRefreshAutoNormalFooter footerWithRefreshingBlock:^{ //Call this Block When enter the refresh status automatically }]; ``` UIWebView01-The drop-down refresh objc //Add the control of The drop-down refresh self.webView.scrollView.mj_header = [MJRefreshNormalHeader headerWithRefreshingBlock:^{ //Call this Block When enter the refresh status automatically }]; Remind ARC iOS>=6.0 iPhone \ iPad screen anyway Hope If you find bug when used，Hope you can Issues me，Thank you or try to download the latest code of this framework to see the BUG has been fixed or not） If you find the function is not enough when used，Hope you can Issues me，I very much to add more useful function to this framework ，Thank you ! If you want to contribute code for MJRefresh，please Pull Requests me If you use MJRefresh in your develop app，Hope you can go toCocoaControlsto add the iTunes path of you app，I Will install your app，and according to the usage of many app，to be a better design and improve to MJRefresh，Thank you ! StepO1（WeChat is just an Example，Explore“Your app name itunes”） StepO2 StepO3 StepO4