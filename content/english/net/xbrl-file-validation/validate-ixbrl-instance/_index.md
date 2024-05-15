---
title: Validate iXBRL Instance
linktitle: Validate iXBRL Instance
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 10
url: /net/xbrl-file-validation/validate-ixbrl-instance/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl.Inline;
using Aspose.Finance.Xbrl.Validator;
using System;
using System.Collections.Generic;

namespace CSharp.ValidateXbrlFiles
{
    class ValidateIxbrlInstance
    {
        public static void Run()
        {
            // ExStart:1
            // Source directory
            string sourceDir = "Your Source Directory";

            InlineXbrlDocument document = new InlineXbrlDocument(sourceDir + @"account_1.html");
            document.Validate();
            if (document.ValidationErrors.Count > 0)
            {
                List<ValidationError> validationErrors = document.ValidationErrors;
            }
            // ExEnd:1

            Console.WriteLine("ValidateIxbrlInstance executed successfully.");
        }
    }
}

```
