--- 
title: "Tworzenie uprawnień do zamawiania produktów w imieniu innej osoby"
description: "W tej procedurze pokazano, jak przyznać pracownikom uprawnienia do przygotowywania zapotrzebowań na zakup w imieniu innych pracowników."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8f12f9eb949034f9bef91d93f31a0f3373e39e98
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Tworzenie uprawnień do zamawiania produktów w imieniu innej osoby

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak przyznać pracownikom uprawnienia do przygotowywania zapotrzebowań na zakup w imieniu innych pracowników. Innymi słowy „wystawca” zapotrzebowania na zakup może utworzyć zapotrzebowanie dla innej osoby, zwanej „zleceniodawcą”. W procedurze również pokazano, jak przyznać pracownikowi uprawnienie do zamawiania towarów i usług w innych firmach i jednostkach operacyjnych. Zazwyczaj te zadania wykonuje kierownik ds. zakupów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Przyznawanie uprawnienia do wprowadzania zapotrzebowań na zakup w imieniu innego pracownika
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zasady > Uprawnienia zapotrzebowania na zakup.
    * Upewnij się, że w polu Bieżący widok zaznaczono wartość Wg wystawcy.  Na liście w lewym okienku są wyświetlane osoby, którym można przyznać uprawnienie do przygotowywania zapotrzebowań w imieniu innych osób.  
2. Wybierz osobę, której chcesz przyznać uprawnienia (wystawcę).
3. Kliknij przycisk Dodaj.
4. Znajdź i zaznacz osobę, którą chcesz dodać jako zleceniodawcę.
    * Zleceniodawca jest osobą, w imieniu której wystawca może tworzyć zapotrzebowania.  
    * W polu Autoryzacja zaznacz opcję Określony, jeśli wystawca powinien mieć możliwość tworzenia zapotrzebowań na zakup w imieniu wybranego pracownika. Wybierz opcję Raportowanie, jeżeli wystawca powinien mieć również możliwość tworzenia zapotrzebowań na zakup w imieniu wszystkich pracowników podlegających wybranemu pracownikowi.  
5. W polu Data wprowadzenia wpisz datę.
6. W polu Data wygaśnięcia wprowadź datę.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Wyświetlanie wystawców mających uprawnienie do tworzenia zapotrzebowań na zakup dla wybranego pracownika
1. W polu Bieżący widok wybierz wartość „Wg zleceniodawcy”.
    * Ten widok zawiera listę wystawców, którym przyznano uprawnienie do tworzenia zapotrzebowań na zakup w imieniu wybranego pracownika.  
2. Za pomocą szybkiego filtru znajdź pracownika, który właśnie został dodany jako zleceniodawca.
3. Zaznacz zleceniodawcę.
    * Na liście wystawców znajdują się osoby uprawnione do zamawiania towarów w imieniu zleceniodawcy wybranego w lewym okienku.   W tym miejscu można dodawać kolejnych wystawców.   Ten widok umożliwia również przyznanie uprawnień zleceniodawcy pozwalających tworzyć zapotrzebowania w firmach i jednostkach operacyjnych, które nie są podstawowymi firmami ani jednostkami operacyjnymi danej osoby.  


