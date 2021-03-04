---
title: Obsługa BOM dla modelu konfiguracji produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcdf4b735587b76b7f761f59c56da1ca358a2e37
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435081"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Obsługa BOM dla modelu konfiguracji produktu

[!include [banner](../../includes/banner.md)]

Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu. Do utworzenia tej procedury użyto modelu Głośnik o wysokiej jakości zawartego w firmie demonstracyjnej USMF.


## <a name="add-a-bom-line"></a>Dodawanie wiersza BOM
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Modele konfiguracji produktu.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Do wykonania tej procedury wybierz towar Głośnik o wysokiej jakości.  
4. Na liście kliknij łącze w wybranym wierszu.
5. Rozwiń sekcję Wiersze BOM.
6. Kliknij przycisk Dodaj.
7. W polu Nazwa wpisz wartość.
8. Wypełnij pole Opis.
9. Kliknij przycisk Zapisz.

## <a name="add-bom-line-details"></a>Dodawanie szczegółów wiersza BOM
1. Kliknij opcję Szczegóły wiersza BOM.
2. W polu Numer towaru wprowadź lub wybierz wartość.
    * Można na przykład wybrać towar M0055.  
    * Dla każdej właściwości wiersza BOM można wybrać, czy ma ona wartość stałą czy też jest mapowana do atrybutu.  
3. Zaznacz pole wyboru Ustaw.
4. W polu Obliczanie wybierz opcję Tak.
    * Ustawienie we właściwości Obliczanie wartości Tak gwarantuje, że wiersz BOM zostanie uwzględniony w obliczeniach kosztów.  
5. Kliknij kartę Ustawienia.
6. Zaznacz pole wyboru Ustaw.
7. Wprowadź liczbę w polu Ilość.
    * Pole ilości określa, jaka część towaru zostanie uwzględniona na liście składowej. To pole jest idealnym kandydatem do mapowania atrybutów.  
8. Kliknij kartę Wymiar.
    * Sprawdź, czy którykolwiek wymiar produktu jest aktywny i w związku z tym musi mieć przypisaną wartość lub atrybut.  
9. Kliknij przycisk OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]