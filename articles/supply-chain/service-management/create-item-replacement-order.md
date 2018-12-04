---
title: "Tworzenie zamówienia wymiany towaru"
description: "Zamówienia zwrotu towaru tworzy się zazwyczaj po odebraniu i sprawdzeniu zwróconego towaru."
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1f0cd629658972f98e2233dfa287940c4444b82a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="create-an-item-replacement-order"></a>Tworzenie zamówienia wymiany towaru 

[!include [banner](../includes/banner.md)]


Zamówienia zwrotu towaru tworzy się zazwyczaj po odebraniu i sprawdzeniu zwróconego towaru. Jeśli jednak towar musi być wymieniony przed zwrotem lub jeśli pierwszy towar nie został zwrócony, natychmiast po utworzeniu zamówienia zwrotu można utworzyć zamówienie wymiany towaru.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>Utwórz zamówienie wymiany po otrzymaniu towary, który jest zwracany.

1.  Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.

2.  Utwórz nowe zamówienie zwrotu lub wybierz zwrócony towar z listy, aby otworzyć formularz **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**.

3.  Kliknij opcję **Wiersz zwrotu**, a następnie wybierz opcję **Pozycja zastępcza**.

4.  Wybierz towar do zastępowania zwróconych towarów. Wprowadź specyfikacje towaru, a następnie kliknij przycisk **Zastosuj**.

5.  Kliknij opcję **Dokument dostawy**, aby wygenerować dokument dostawy dla zamówienia zwrotu. Zamówienie sprzedaży jest generowane dla wybranego towaru zastępczego.
    
    Po utworzeniu zamówienia sprzedaży dla towaru zastępczego następuje automatyczne wyszukiwanie umów sprzedaży, a jeśli istnieje odpowiednia umowa sprzedaży, zostanie zastosowana do zamówienia sprzedaży.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>Utwórz zamówienie wymiany, zanim pojawi się towar, który powinien być zwrócony

1.  Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.

2.  Utwórz nowe zamówienie zwrotu lub wybierz zamówienie zwrotu z listy, aby otworzyć formularz **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**.

3.  Kliknij przycisk **Znajdź zamówienie sprzedaży**, jeśli chcesz zidentyfikować zamówienie sprzedaży dla zwróconego towaru. Wypełnij formularz **Znajdź zamówienie sprzedaży**, a następnie kliknij przycisk **OK**. Formularz zostanie zamknięty i nastąpi powrót do formularza **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**. Wiersz zamówienia sprzedaży dla zwróconego towaru jest kopiowany do zamówienia zwrotu.

4.  Kliknij przycisk **Zamówienie wymiany**, a zostanie otwarty formularz **Tworzenie zamówienia sprzedaży**.

5.  Zaznacz pole wyboru **Kopiuj wiersze zamówienia zwrotu**, aby przesłać dane z zamówienia zwrotu wybranego w formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** do tego zamówienia sprzedaży.

6.  Odpowiednio do potrzeb wprowadź lub zmodyfikuj szczegóły.
    
    Jeśli określono zamówienie sprzedaży w kroku 3 i jeśli wiersz zamówienia sprzedaży dla zwróconego towaru jest połączony z umową sprzedaży, identyfikator odpowiedniej umowy sprzedaży stosowany dla zamówienia wymiany towaru będzie automatycznie wyświetlany w polu **Identyfikator umowy sprzedaży**.

7.  Kliknij przycisk **OK**, aby zamknąć formularz **Tworzenie zamówienia sprzedaży** i otworzyć formularz **Zamówienie sprzedaży**, w którym można kontynuować wprowadzanie danych nowego zamówienia sprzedaży. Wszelkie obowiązujące wiersze zamówienia zwrotu zostaną skopiowane do nowego zamówienia sprzedaży. 
    
    Jeżeli identyfikator umowy sprzedaży jest automatycznie wyświetlany w polu **Identyfikator umowy sprzedaży**, to umowa sprzedaży została połączona z nagłówkiem zamówienia sprzedaży dla zamówienia wymiany towaru. W przypadku istnienia zobowiązania w umowie sprzedaży, które nie zostało jeszcze wypełnione, gdy zamówienie sprzedaży jest tworzone, zanim umowa sprzedaży stracił ważność, ustal, co łączy wiersz umowy sprzedaży i wiersz zamówienia sprzedaży. Dlatego informacje z umowy sprzedaży, np. cena towaru, kopiowane są fo nowego wiersza zamówienia sprzedaży. 
  



