---
title: Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach
description: Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7961cfb4ad0e20c49d327d83f56c08811598ac1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435229"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach

[!include [banner](../../includes/banner.md)]

Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań. Pierwsze 4 nagrania obejmują skonfigurowanie danych wymaganych do wykonania tej procedury. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. To zadanie jest zazwyczaj wykonywane przez projektanta produktów.


## <a name="select-the-product"></a>Wybieranie produktu
1. Kliknij pozycję Obsługa zwolnionego produktu.
2. Kliknij opcję Zwolnione produkty.
3. Na liście oznacz wybrany wiersz.
    * Znajdź zwolniony produkt główny z technologią konfiguracji opartej na wymiarach, który utworzono w pierwszym przewodniku po zadaniach w tej sekwencji.  
4. W okienku akcji kliknij pozycję Konstruuj.
5. Kliknij opcję Wersje BOM.

## <a name="create-new-bom-and-bom-version"></a>Tworzenie nowej BOM i wersji BOM
1. Kliknij przycisk Nowy.
2. Kliknij opcję BOM i wersja BOM.
3. W polu Nazwa wpisz wartość.
    * Ustawianie oddziału  
    * W tej procedurze nie ustawimy konkretnego oddziału dla BOM.  
4. Kliknij przycisk OK.
5. Kliknij przycisk Nowy.
    * W tej procedurze dodamy cztery wiersze do BOM. Dwa wiersze reprezentują opcje kabla, a dwa opcje szafy.  
6. Na liście oznacz wybrany wiersz.
7. W polu Numer towaru wprowadź lub wybierz wartość.
    * Wybierz towar o numerze A0001 HDMI 6' Cables (kable HDMI o długości 1,8 m).  
8. W polu Grupa konfiguracji wpisz lub wprowadź wartość.
    * Wybierz grupę konfiguracji Kabel utworzoną w przewodniku 4 w tej sekwencji.  
9. Kliknij przycisk Nowy.
    * Wybierz towar o numerze A0002 HDMI 6' Cables (kable HDMI o długości 3,6 m).  
10. Na liście oznacz wybrany wiersz.
11. W polu Numer towaru wprowadź lub wybierz wartość.
12. W polu Grupa konfiguracji wpisz lub wprowadź wartość.
    * Ponownie zaznacz grupę konfiguracji Kabel.  
13. Kliknij przycisk Nowy.
14. Na liście oznacz wybrany wiersz.
15. W polu Numer towaru wprowadź lub wybierz wartość.
    * Wybierz towar o numerze D0002 Cabinet (Szafa).  
16. W polu Grupa konfiguracji wpisz lub wprowadź wartość.
    * Dla tego wiersza BOM wybierz grupę konfiguracji Szafa.  
17. Kliknij przycisk Nowy.
18. Na liście oznacz wybrany wiersz.
19. W polu Numer towaru wprowadź lub wybierz wartość.
    * Jako ostatni wiersz BOM wybierz towar o numerze 0007 StandardCabinet (Standardowa szafa).  
20. W polu Grupa konfiguracji wpisz lub wprowadź wartość.
    * Dla ostatniego wiersza BOM wybierz grupę konfiguracji Szafa.  

## <a name="approve-and-activate"></a>Zatwierdź i aktywuj
1. Zamknij stronę.
2. Kliknij przycisk Zatwierdź.
3. W polu Zatwierdzone przez wprowadź lub wybierz wartość.
4. W polu Czy chcesz także zatwierdzić listę składową (BOM)? zaznacz wartość Tak.
5. Kliknij przycisk OK.
6. Kliknij Aktywacja.

