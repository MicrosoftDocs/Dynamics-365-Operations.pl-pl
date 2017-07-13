---
title: "Konfigurowanie funkcjonalności logowania rozszerzonego w programach Cloud POS i MPOS"
description: Ten temat omawia opcje konfigurowania rozszerzonego logowania do aplikacji Cloud POS i Retail Modern POS (MPOS).
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 0b7e5ed451497aea1c2ce798af2b717705538d47
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017



---

# Konfigurowanie funkcjonalności logowania rozszerzonego w programach Cloud POS i MPOS
<a id="set-up-extended-logon-functionality-for-cloud-pos-and-mpos" class="xliff"></a>

[!include[banner](includes/banner.md)]


Ten temat omawia opcje konfigurowania rozszerzonego logowania do aplikacji Cloud POS i Retail Modern POS (MPOS).

Konfigurowanie logowania rozszerzonego
<a id="setting-up-extended-logon" class="xliff"></a>
=========================

Konfiguracje masek kodów kreskowych można znaleźć w oknie **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktu sprzedaży** &gt; **Profile funkcji**. Na skróconej karcie **Funkcje** znajdują się następujące opcje, które są związane z logowaniem rozszerzonym.

### Logowanie się pracowników za pomocą kodu kreskowego
<a id="staff-bar-code-logon" class="xliff"></a>

Gdy wybrana jest opcja **Logowanie się pracowników za pomocą kodu kreskowego**, pracownicy, którzy do swoich poświadczeń w punkcie sprzedaży mają przypisane logowanie rozszerzone, mogą logować się za pomocą kodu kreskowego.

### Logowanie się pracowników za pomocą kodu kreskowego wymaga hasła
<a id="staff-bar-code-logon-requires-password" class="xliff"></a>

Jeśli włączona jest opcja **Logowanie się pracowników za pomocą kodu kreskowego wymaga hasła**, funkcja logowanie się pracowników za pomocą kodu kreskowego wybiera tylko tego pracownika, który jest przypisany do przedstawionego logowania rozszerzonego. Pracownicy muszą nadal podać hasło, nawet gdy ta opcja jest wybrana.

### Logowanie się pracowników za pomocą karty
<a id="staff-card-logon" class="xliff"></a>

Gdy wybrana jest opcja **Logowanie się pracowników za pomocą karty**, pracownicy, którzy do swoich poświadczeń w punkcie sprzedaży mają przypisane logowanie rozszerzone, mogą logować się za pomocą paska magnetycznego.

### Logowanie się pracowników za pomocą karty wymaga hasła
<a id="staff-card-logon-requires-password" class="xliff"></a>

Jeśli włączona jest opcja **Logowanie się pracowników za pomocą karty wymaga hasła**, logowanie się pracowników za pomocą karty wybiera tylko tego pracownika, który jest przypisany do przedstawionego logowania rozszerzonego. Pracownicy muszą nadal podać hasło, nawet gdy ta opcja jest wybrana.

Przypisywanie logowania rozszerzonego
<a id="assigning-an-extended-logon" class="xliff"></a>
===========================

Domyślnie tylko menedżerowie mogą przypisywać pracownikom logowanie rozszerzone. Aby przypisać logowanie rozszerzone, przejdź do opcji **Logowanie rozszerzone** w aplikacji punktu sprzedaży. Następnie wyszukaj pracownika, wpisując w polu wyszukiwania jego identyfikator operatora. Wybierz pracownika, a następnie kliknij przycisk **Przypisz**. Na następnej stronie przeciągnij lub zeskanuj kartę lub kod kreskowy do logowania rozszerzonego, aby przypisać pracownika. Jeśli odczyt danych się powiedzie, przycisk **OK** stanie się aktywny. Kliknij **OK**, aby zapisać logowanie rozszerzone dla tego pracownika.

Anulowanie przypisania logowania rozszerzonego
<a id="deleting-an-extended-logon" class="xliff"></a>
==========================

Aby anulować przypisanie logowania rozszerzonego do pracownika, znajdź pracownika za pomocą operacji **Logowanie rozszerzone**. Wybierz pracownika, a następnie kliknij przycisk **Anuluj przypisanie**. Wszystkie poświadczenia logowania rozszerzonego przypisane do tego pracownika są usuwane.

Rozszerzanie logowania rozszerzonego
<a id="extending-extended-logon" class="xliff"></a>
========================

Usługę logowania można rozszerzyć o obsługę dodatkowych urządzeń do logowania rozszerzonego, takich jak skanery ręczne. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją rozszerzania punktu sprzedaży.

Używanie logowania rozszerzonego
<a id="using-extended-logon" class="xliff"></a>
====================

Jeśli logowanie rozszerzone jest skonfigurowane i pracownik ma przypisany kod kreskowy lub pasek magnetyczny, pracownik musi tylko przeciągnąć kartę magnetyczną w czytniku lub zeskanować kod kreskowy, gdy na ekranie wyświetlana jest strona logowania punktu sprzedaży. Jeśli logowanie wymaga podania hasła, wyświetla się również monit o podanie hasła.




