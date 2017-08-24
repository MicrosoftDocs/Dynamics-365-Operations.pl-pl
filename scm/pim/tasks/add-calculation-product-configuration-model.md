--- 
title: Dodawanie obliczenia do modelu konfiguracji produktu
description: "W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 9ac2d9bcc316a57941136c248a0c5ff030a1fe49
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Dodawanie obliczenia do modelu konfiguracji produktu

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu. Pokazuje sposób tworzenia wyrażenia logicznego za pomocą operatora „If”, aby ustawić wysokość głośnika na 10 dla białych głośników i na 15 dla wszystkich pozostałych wykończeń obudowy. Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.


## <a name="add-a-calculation"></a>Dodawanie obliczenia

## <a name="create-calculation-expression"></a>Tworzenie wyrażenia obliczenia
1. Kliknij opcję Edytuj wyrażenie.
2. W polu ConstraintBody wpisz „If[CabinetFinish=="Biały", 10, 15]”.
3. Kliknij przycisk Sprawdź poprawność.
4. Kliknij przycisk Zamknij.
5. Kliknij przycisk OK.


