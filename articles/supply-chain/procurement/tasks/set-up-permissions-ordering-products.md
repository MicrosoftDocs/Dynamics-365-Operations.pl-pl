---
title: Tworzenie uprawnień do zamawiania produktów w imieniu innej osoby
description: W tym artykule pokazano, jak przyznać pracownikom uprawnienia do przygotowywania zapotrzebowań na zakup w imieniu innych pracowników.
author: GalynaFedorova
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3053f28fdf97637b1da5f644f64676bfd10fb6a0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854218"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Tworzenie uprawnień do zamawiania produktów w imieniu innej osoby

[!include [banner](../../includes/banner.md)]

W tym artykule pokazano, jak przyznać pracownikom uprawnienia do przygotowywania zapotrzebowań na zakup w imieniu innych pracowników. Innymi słowy „wystawca” zapotrzebowania na zakup może utworzyć zapotrzebowanie dla innej osoby, zwanej „zleceniodawcą”. W procedurze również pokazano, jak przyznać pracownikowi uprawnienie do zamawiania towarów i usług w innych firmach i jednostkach operacyjnych. Zazwyczaj te zadania wykonuje kierownik ds. zakupów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Przyznawanie uprawnienia do wprowadzania zapotrzebowań na zakup w imieniu innego pracownika
1. W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Ustawienia > Zasady > Uprawnienia zapotrzebowania na zakup**. Upewnij się, że w polu **Bieżący widok** zaznaczono wartość **Wg wystawcy**. Na liście w lewym okienku są wyświetlane osoby, którym można przyznać uprawnienie do przygotowywania zapotrzebowań w imieniu innych osób.  
2. Wybierz osobę, której chcesz przyznać uprawnienia (wystawcę).
3. Wybierz opcję **Dodaj**.
4. Znajdź i zaznacz osobę, którą chcesz dodać jako zleceniodawcę.
    - Zleceniodawca jest osobą, w imieniu której wystawca może tworzyć zapotrzebowania.  
    - W polu **Autoryzacja** zaznacz opcję **Określony**, jeśli wystawca powinien mieć możliwość tworzenia zapotrzebowań na zakup w imieniu wybranego pracownika. Wybierz opcję **Raportowanie**, jeżeli wystawca powinien mieć również możliwość tworzenia zapotrzebowań na zakup w imieniu wszystkich pracowników podlegających wybranemu pracownikowi.  
5. W polu **Data wprowadzenia** wpisz datę.
6. W polu **Data wygaśnięcia** wprowadź datę.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Wyświetlanie wystawców mających uprawnienie do tworzenia zapotrzebowań na zakup dla wybranego pracownika
1. W polu **Bieżący widok** wybierz wartość **Wg zleceniodawcy**. Ten widok zawiera listę wystawców, którym przyznano uprawnienie do tworzenia zapotrzebowań na zakup w imieniu wybranego pracownika.  
2. Za pomocą szybkiego filtru znajdź pracownika, który właśnie został dodany jako zleceniodawca.
3. Zaznacz zleceniodawcę. Na liście wystawców znajdują się osoby uprawnione do zamawiania towarów w imieniu zleceniodawcy wybranego w lewym okienku.  W tym miejscu można dodawać kolejnych wystawców. Ten widok umożliwia również przyznanie uprawnień zleceniodawcy pozwalających tworzyć zapotrzebowania w firmach i jednostkach operacyjnych, które nie są podstawowymi firmami ani jednostkami operacyjnymi danej osoby.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]