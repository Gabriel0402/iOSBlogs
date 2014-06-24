
```
- (void)showTutorialsScreen:(BOOL)animated
{
    NUDTutorialsViewController *tutorialsVC = [[NUDTutorialsViewController alloc] init];
    UINavigationController *tutorialsNavController = [[UINavigationController alloc] initWithRootViewController:tutorialsVC];
    
    [self switchRootViewController:tutorialsNavController animated:animated completion:nil];
}
```

```
- (void)showLoadingScreen:(BOOL)animated
{
    NUDLoadingViewController *loadingVC = [[NUDLoadingViewController alloc] init];
    
    [self switchRootViewController:loadingVC animated:animated completion:nil];
}
```

```
- (void)showMainScreen:(BOOL)animated
{
    NUDMainViewController *mainVC = [[NUDMainViewController alloc] init];
    UINavigationController *mainNavController = [[UINavigationController alloc] initWithRootViewController:mainVC];
    
    [self switchRootViewController:mainNavController animated:animated completion:nil];
}
```

You can use this code to switch rootviewcontroller

```
- (void)switchRootViewController:(UIViewController *)aRootViewController animated:(BOOL)animated completion:(void(^)())completion
{
    if (animated) {
        [UIView transitionWithView:self.window duration:0.3 options:UIViewAnimationOptionTransitionCrossDissolve animations:^{
            BOOL oldState = [UIView areAnimationsEnabled];
            [UIView setAnimationsEnabled:NO];
            self.window.rootViewController = aRootViewController;
            [UIView setAnimationsEnabled:oldState];
        } completion:^(BOOL finished) {
            if (completion) completion();
        }];
    }
    else {
        self.window.rootViewController = aRootViewController;
        if (completion) completion();
    }
}

```