
# Anatoly Kravtsov
Vocational psychologist

### Contact info:
  * [Github](https://github.com/Toriku/)
  * email: anatoly.kravtsov@gmail.com
  * Telegram: @RealToriku

### Skills:
  * Python
  * Django
  * HTML5
  * CSS

### English level:

B2/C1 (IELTS: Reading: 9.0, Listening: 8.5, Writing: 6.5, Speaking: 6.5)

### Code example:
```python
@login_required
def take_test_view(request, test_slug):
    user = request.user
    test = get_object_or_404(Test, slug=test_slug)
    
    if not FullProftestResult.objects.filter(user=user).exists():
        return redirect("profile")

    if test.id in user.done_proftest_tests:
        return redirect("profile")
        
    else:
        context = {"test": test}
        return render(request, "take_test.html", context)
```
