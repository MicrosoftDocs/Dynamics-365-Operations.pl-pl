---
title: Dodawanie obliczenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 268baa4b518f6df52d4393f7278a79cbe1733844
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812688"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Dodawanie obliczenia do modelu konfiguracji produktu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak dodać nowe obliczenie do modelu konfiguracji produktu. Pokazuje sposób tworzenia wyrażenia logicznego za pomocą operatora „If”, aby ustawić wysokość głośnika na 10 dla białych głośników i na 15 dla wszystkich pozostałych wykończeń obudowy. Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.


## <a name="add-a-calculation"></a>Dodawanie obliczenia

## <a name="create-calculation-expression"></a>Tworzenie wyrażenia obliczenia
1. Kliknij opcję Edytuj wyrażenie.
2. W polu ConstraintBody wpisz „If[CabinetFinish=="Biały", 10, 15]”.
3. Kliknij przycisk Sprawdź poprawność.
4. Kliknij przycisk Zamknij.
5. Kliknij przycisk OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]