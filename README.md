# oc-vqmod-filemanager-select_dir
An vqmod extension to add functionality of selecting directory instead of images
And also multiupload images

#You must do a small wrok on this files:
this file:
```
admin/view/javascript/common.js
```

and this one:
```
admin/view/javascript/common-rtl.js
```

find:
```
url: 'index.php?route=common/filemanager&token=' + getURLVar('token') + '&target=' + $(element).parent().find('input').attr('id') + '&thumb=' + $(element).attr('id'),
```
replace with:
```
url: 'index.php?route=common/filemanager&token=' + getURLVar('token') + '&target=' + $(element).parent().find('input').attr('id') + '&thumb=' + $(element).attr('id')+'&directory='+$(element).parent().find('input').val() ,
```
# Sample Use:
```HTML
<div class="form-group">
	<label class="col-sm-2 control-label">Select Directory</label>
	<div class="col-sm-10">
	<a href="" id="thumb-images_url" data-toggle="image" class="img-thumbnail">
		<img src="<?php echo $thumb; ?>" alt="" title="" data-placeholder="<?php echo $placeholder; ?>" />
	</a>
		<input type="text" name="images_url" value="<?php echo $images_url; ?>" id="input-images_url" />
	</div>				
</div>
```
Not That I used type="text" insted of ~~type="hidden"~~
