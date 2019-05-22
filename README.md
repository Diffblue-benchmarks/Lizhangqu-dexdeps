dexdeps
=======

### Sample

```
List<DexData> dexDataList = DexData.open(apkFile);
if (dexDataList != null && dexDataList.size() > 0) {
    for (DexData dexData : dexDataList) {
        ClassRef[] references = dexData.getReferences();
        if (references != null) {
            for (ClassRef classRef : references) {
                System.out.println("classRef:" + classRef + " internal:" + classRef.isInternal());

                FieldRef[] fieldArray = classRef.getFieldArray();
                if (fieldArray != null && fieldArray.length > 0) {
                    for (FieldRef fieldRef : fieldArray) {
                        System.out.println("fieldRef:" + fieldRef + " internal:" + fieldRef.isInternal());
                    }
                }
                MethodRef[] methodArray = classRef.getMethodArray();

                if (methodArray != null && methodArray.length > 0) {
                    for (MethodRef methodRef : methodArray) {
                        System.out.println("methodRef:" + methodRef + " internal:" + methodRef.isInternal());
                    }
                }
            }
        }
    }
}
```