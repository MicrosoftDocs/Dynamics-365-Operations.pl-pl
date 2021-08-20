---
title: Obsługa BOM dla modelu konfiguracji produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 173022d40a5c1354cbe05c171a8921e733d908d065b10889f9cbe0e87f3e98fa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781472"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Obsługa BOM dla modelu konfiguracji produktu

[!include [banner](../../includes/banner.md)]

Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu. Do utworzenia tej procedury użyto modelu Głośnik o wysokiej jakości zawartego w firmie demonstracyjnej USMF.

## <a name="add-a-bom-line"></a>Dodawanie wiersza BOM

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Na liście znajdź i zaznacz odpowiedni rekord.
    * Do wykonania tej procedury wybierz towar Głośnik o wysokiej jakości.  
1. Na liście wybierz łącze w wybranym wierszu.
1. Rozwiń sekcję **Wiersze BOM**.
1. Wybierz opcję **Dodaj**.
1. W polu **Nazwa** wpisz wartość.
1. W polu **Opis** wpisz wartość.
1. Wybierz opcję **Zapisz**.

## <a name="add-bom-line-details"></a>Dodawanie szczegółów wiersza BOM

1. Wybierz opcję **Szczegóły wiersza BOM**.
2. W polu **Kod towaru** wpisz lub wprowadź wartość.
    * Można na przykład wybrać towar M0055.  
    * Dla każdej właściwości wiersza BOM można wybrać, czy ma ona wartość stałą czy też jest mapowana do atrybutu.  
3. Zaznacz pole wyboru **Ustaw**.
4. W polu **Obliczanie** wybierz opcję *Tak*.
    * Ustawienie we właściwości **Obliczanie** wartości *Tak* gwarantuje, że wiersz BOM zostanie uwzględniony w obliczeniach kosztów.  
5. Kliknij kartę **Konfiguracja**.
6. Zaznacz pole wyboru **Ustaw**.
7. W polu **Ilość** wpisz liczbę.
    * Pole ilości określa, jaka część towaru zostanie uwzględniona na liście składowej. To pole jest idealnym kandydatem do mapowania atrybutów.  
8. Wybierz kartę **Wymiary**.
    * Sprawdź, czy którykolwiek wymiar produktu jest aktywny i w związku z tym musi mieć przypisaną wartość lub atrybut.  
9. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]