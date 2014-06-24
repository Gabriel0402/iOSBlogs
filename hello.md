
Use this source code when you want to switch rootviewcontroller in AppDelegate.

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
