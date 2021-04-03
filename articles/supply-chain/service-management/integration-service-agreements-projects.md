---
title: Integracja umów serwisowych i projektów
description: Podczas pracy z wierszami umów serwisowych i umowami serwisowymi wykorzystywane są dane ustawiane w obszarach modułu Zarządzanie projektami i ich księgowanie.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd0a7de17e8ff098220fd183b714b77225cc217f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247317"
---
# <a name="integration-for-service-agreements-and-projects"></a>Integracja umów serwisowych i projektów 

[!include [banner](../includes/banner.md)]


Podczas pracy z wierszami umów serwisowych i umowami serwisowymi wykorzystywane są dane ustawiane w następujących obszarach modułu **Zarządzanie projektami i ich księgowanie**.

## <a name="project-prices"></a>Ceny projektu

Koszt własny i cena sprzedaży związane z transakcją umowy serwisowej pochodzą z konfiguracji kosztu własnego, która dotyczy projektu związanego z umową serwisową. Koszt własny i cena sprzedaży mogą być ustawiane dla kategorii, projektów i pracowników. 

## <a name="project-validation"></a>Weryfikacja projektu

Projekty, pracownicy i kategorie dostępne do wyboru w wierszu umowy serwisowej można ograniczać za pomocą konfiguracji sprawdzania poprawności w module **Zarządzanie projektami i ich księgowanie**. Konfiguracja sprawdzania poprawności umożliwia łączenie pracowników, projektów i kategorii na potrzeby kontroli dostępu. 

## <a name="project-line-properties"></a>Właściwości wiersza projektu

Właściwość wiersza umowy serwisowej jest wprowadzana automatycznie.

Właściwości wierszy są tworzone w formularzu **Właściwości wiersza** w module **Zarządzanie projektami i ich księgowanie**. Właściwość wiersza wprowadzona w umowie serwisowej jest związana z projektem wybranym dla umowy serwisowej, a później dziedziczona przez wiersz umowy serwisowej. 

## <a name="default-offset-accounts"></a>Domyślne konta przeciwstawne

Podczas wprowadzania transakcji wydatku automatycznie jest dla niej wybierane domyślne konto przeciwstawne wydatku. Domyślne konto wydatku jest konfigurowane dla projektu związanego z bieżącą umową serwisową.

## <a name="project-categories"></a>Kategorie projektu

Kategorie dostępne dla wierszy umowy serwisowej są ustawiane w formularzu **Kategorie projektu** w module **Zarządzanie projektami i ich księgowanie**. 

> [!NOTE]
> <P>Kategorie, które mają zaznaczone pole wyboru <STRONG>Aktywne w arkuszach</STRONG> na karcie <STRONG>Projekt</STRONG> w formularzu <STRONG>Kategorie projektu</STRONG>, są dostępne do wyboru. Jednak jeśli pole wyboru <STRONG>Nieaktywne kategorie</STRONG> jest zaznaczone na karcie <STRONG>Arkusze</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie projektami i ich księgowanie</STRONG>, wszystkie kategorie są dostępne do wyboru.</P>

## <a name="project-parameters"></a>Parametry projektu

Jeśli jest zaznaczone pole wyboru **Zwolnieni pracownicy** na karcie **Arkusze** w formularzu **Parametry modułu Zarządzanie projektami i ich księgowanie**, można wybierać nieaktywnych pracowników i aktywnych pracowników w formularzach **Umowy serwisowe** i **Zlecenia serwisowe**.

Ponadto można włączyć pola **Godzina rozpoczęcia** i **Godzina zakończenia** na karcie **Projekt** w formularzu **Zlecenia serwisowe**, aby wprowadzić godziny rozpoczęcia i zakończenia w wierszach zlecenia serwisowego.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>Włączanie funkcji godzin rozpoczęcia i zakończenia w zleceniach serwisowych

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**.

2.  Kliknij kartę **Arkusze**, a następnie zaznacz pole wyboru **Pokaż godziny rozpoczęcia/zakończenia**.

3.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Arkusze** \> **Nazwy arkuszy**.

4.  Wybierz nazwę arkusza związanego ze zleceniem serwisowym.

5.  Kliknij kartę **Ogólne**, a następnie zaznacz pole wyboru **Pokaż godziny rozpoczęcia/zakończenia**.


> [!NOTE]
> <P>Wybierz nazwę arkusza dla zlecenia serwisowego w polu <STRONG>Godzina</STRONG> na karcie <STRONG>Arkusze</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG>.</P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]