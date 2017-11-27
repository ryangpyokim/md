<<<<<<< HEAD
Synchronization
-------------------

StackEdit can be combined with "icon-provider-gdrive" **Google Drive** and <i class="icon-provider-dropbox"></i> **Dropbox** to have your documents saved in the *Cloud*. The synchronization mechanism takes care of uploading your modifications or downloading the latest version of your documents.

> **Note:**

> - Full access to **Google Drive** or **Dropbox** is required to be able to import any document in StackEdit. Permission restrictions can be configured in the settings.
> - Imported documents are downloaded in your browser and are not transmitted to a server.
> - If you experience problems saving your documents on Google Drive, check and optionally disable browser extensions, such as Disconnect.

```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```

```sql
create table temp_synckey01 as
select * from (
  select /*+ leading(ch pa) use_nl(ch pa) */
        pa.sync_sop_key as g3key
      , pa.sop_key as pa_sop
      , ch.sop_key as ch_sop
      , ch.parnt_sop_key
      , count(1) over (partition by pa.sop_key) ch_count  -- ch_count + 1 = ch + pa
  from sop ch -- 자식
     , sop pa -- 부모
  where 1=1
  and ch.parnt_sop_key = pa.sop_key
 ) where ch_count >= 2;
 
create table temp_synckey01_upd as
select pa_sop as spk -- 35,384
from temp_synckey01
union
select ch_sop as spk -- 73,181
from temp_synckey01;

create table temp_synckey01_del as
select g3key -- ch_sync
from temp_synckey01
union
select pa.sync_sop_key as g3key -- pa_sync  
from sop pa, temp_synckey01 a
where pa.sop_key = a.pa_sop;


```
=======
# md
>>>>>>> parent of 008e306... Update README.md
