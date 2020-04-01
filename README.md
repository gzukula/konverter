# Konvert

done: 
* anyToString
* defaultValueIfMissing
* DateToString
* refactoring for collect import
* @Konvert.Filed
* converter function by using converter (@By) 
* converter function by using raw string literal (@Code)
* simple @Konvertable
* auto generate code like @Konvert when processing @Konvertable
* support multiple @Konvertable processing by adding @To
* refactoring using KonvertPoet and KonvertablePoet
* refactoring using KonvertPoet by adding Import
* remove unused code
* use service to replace resolver
* add BaseProcessor

todo:

* refactoring ContractResolver

---
Flow of the processing of @Konvert (old)
Process()
|- find and filter elements related to the annotation processed
|- resolve elements which are generated by kapt
    |= map to and from by TypeElement 
    |= resolve @Konvert annotation and other related annotations
    |= apply contract or default rules
    |= return resolved meta data from type element
|- resolve poet element by meta data
|- generate kotlin code by poet element

Flow of the processing of @Konvert (new)
Process()
|- find and filter elements related to the annotation processed
|- process type elements annotated by annotation
    |= resolve meta data
    |= revolve relevant annotations
    |= resolve rules
    |= resolve poet element
    |= generate kotlin code
