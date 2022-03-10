---
title: Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach
description: Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f86625821f8a01a6d4949f9dca538a279f52ce9c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565595"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach

[!include [banner](../../includes/banner.md)]

Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań. Pierwsze 4 nagrania obejmują skonfigurowanie danych wymaganych do wykonania tej procedury. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. To zadanie jest zazwyczaj wykonywane przez projektanta produktów.

## <a name="select-the-product"></a>Wybieranie produktu

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Na liście oznacz wybrany wiersz.
    * Znajdź zwolniony produkt główny z technologią konfiguracji opartej na wymiarach, który utworzono w pierwszym przewodniku po zadaniach w tej sekwencji.  
1. W okienku akcji wybierz opcję **Konstruuj**.
1. Wybierz opcję **Wersje BOM**.

## <a name="create-new-bom-and-bom-version"></a>Tworzenie nowej BOM i wersji BOM

1. Wybierz pozycję **Nowy**.
1. Wybierz opcję **BOM i wersja BOM**.
1. W polu **Nazwa** wpisz wartość.
    * Ustawianie oddziału  
    * W tej procedurze nie ustawimy konkretnego oddziału dla BOM.  
1. Kliknij przycisk **OK**.
1. Wybierz pozycję **Nowy**.
    * W tej procedurze dodamy cztery wiersze do BOM. Dwa wiersze reprezentują opcje kabla, a dwa opcje szafy.  
1. Na liście oznacz wybrany wiersz.
1. W polu **Kod towaru** wpisz lub wprowadź wartość.
    * Wybierz towar o numerze A0001 HDMI 6' Cables (kable HDMI o długości 1,8 m).  
1. W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.
    * Wybierz grupę konfiguracji kabla utworzoną w przewodniku 4 w tej sekwencji.  
1. Wybierz pozycję **Nowy**.
    * Wybierz towar o numerze A0002 HDMI 6' Cables (kable HDMI o długości 3,6 m).  
1. Na liście oznacz wybrany wiersz.
1. W polu **Kod towaru** wpisz lub wprowadź wartość.
1. W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.
    * Ponownie zaznacz grupę konfiguracji kabla.  
1. Wybierz pozycję **Nowy**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Kod towaru** wpisz lub wprowadź wartość.
    * Wybierz towar o numerze D0002 Cabinet (Szafa).  
1. W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.
    * Dla tego wiersza BOM wybierz grupę konfiguracji szafy.  
1. Wybierz pozycję **Nowy**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Kod towaru** wpisz lub wprowadź wartość.
    * Jako ostatni wiersz BOM wybierz towar o numerze 0007 StandardCabinet (Standardowa szafa).  
1. W polu **Grupa konfiguracji** wpisz lub wprowadź wartość.
    * W ostatnim wierszu BOM wybierz grupę konfiguracji Szafa.  

## <a name="approve-and-activate"></a>Zatwierdź i aktywuj

1. Zamknij stronę.
1. Wybierz opcję **Zatwierdź**.
1. W polu **Zatwierdzone przez** wprowadź lub wybierz wartość.
1. W polu **Czy chcesz także zatwierdzić listę składową (BOM)?** zaznacz wartość *Tak*.
1. Kliknij przycisk **OK**.
1. Wybierz **Aktywuj**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]