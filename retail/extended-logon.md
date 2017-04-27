---
title: "Konfigurowanie funkcjonalności logowania rozszerzonego w programach Cloud POS i MPOS"
description: Ta strona wiki omawia opcje konfigurowania rozszerzonego logowania do aplikacji Cloud POS i Retail Modern POS (MPOS).
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 0dc80784a5c9a7de6009826284cb68f1aee83f70
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a>Konfigurowanie funkcjonalności logowania rozszerzonego w programach Cloud POS i MPOS

Ta strona wiki omawia opcje konfigurowania rozszerzonego logowania do aplikacji Cloud POS i Retail Modern POS (MPOS).

<a name="setting-up-extended-logon"></a>Konfigurowanie logowania rozszerzonego
=========================

Konfiguracje masek kodów kreskowych można znaleźć w oknie **Handel detaliczny i inny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Profile punktu sprzedaży** &gt; **Profile funkcji**. Na skróconej karcie **Funkcje** znajdują się następujące opcje, które są związane z logowaniem rozszerzonym.

### <a name="staff-bar-code-logon"></a>Logowanie się pracowników za pomocą kodu kreskowego

Gdy wybrana jest opcja **Logowanie się pracowników za pomocą kodu kreskowego**, pracownicy, którzy do swoich poświadczeń w punkcie sprzedaży mają przypisane logowanie rozszerzone, mogą logować się za pomocą kodu kreskowego.

### <a name="staff-bar-code-logon-requires-password"></a>Logowanie się pracowników za pomocą kodu kreskowego wymaga hasła

Jeśli włączona jest opcja **Logowanie się pracowników za pomocą kodu kreskowego wymaga hasła**, funkcja logowanie się pracowników za pomocą kodu kreskowego wybiera tylko tego pracownika, który jest przypisany do przedstawionego logowania rozszerzonego. Pracownicy muszą nadal podać hasło, nawet gdy ta opcja jest wybrana.

### <a name="staff-card-logon"></a>Logowanie się pracowników za pomocą karty

Gdy wybrana jest opcja **Logowanie się pracowników za pomocą karty**, pracownicy, którzy do swoich poświadczeń w punkcie sprzedaży mają przypisane logowanie rozszerzone, mogą logować się za pomocą paska magnetycznego.

### <a name="staff-card-logon-requires-password"></a>Logowanie się pracowników za pomocą karty wymaga hasła

Jeśli włączona jest opcja **Logowanie się pracowników za pomocą karty wymaga hasła**, logowanie się pracowników za pomocą karty wybiera tylko tego pracownika, który jest przypisany do przedstawionego logowania rozszerzonego. Pracownicy muszą nadal podać hasło, nawet gdy ta opcja jest wybrana.

<a name="assigning-an-extended-logon"></a>Przypisywanie logowania rozszerzonego
===========================

Domyślnie tylko menedżerowie mogą przypisywać pracownikom logowanie rozszerzone. Aby przypisać logowanie rozszerzone, przejdź do opcji **Logowanie rozszerzone** w aplikacji punktu sprzedaży. Następnie wyszukaj pracownika, wpisując w polu wyszukiwania jego identyfikator operatora. Wybierz pracownika, a następnie kliknij przycisk **Przypisz**. Na następnej stronie przeciągnij lub zeskanuj kartę lub kod kreskowy do logowania rozszerzonego, aby przypisać pracownika. Jeśli odczyt danych się powiedzie, przycisk **OK **stanie się aktywny. Kliknij **OK**, aby zapisać logowanie rozszerzone dla tego pracownika.

<a name="deleting-an-extended-logon"></a>Anulowanie przypisania logowania rozszerzonego
==========================

Aby anulować przypisanie logowania rozszerzonego do pracownika, znajdź pracownika za pomocą operacji **Logowanie rozszerzone**. Wybierz pracownika, a następnie kliknij przycisk **Anuluj przypisanie**. Wszystkie poświadczenia logowania rozszerzonego przypisane do tego pracownika są usuwane.

<a name="extending-extended-logon"></a>Rozszerzanie logowania rozszerzonego
========================

Usługę logowania można rozszerzyć o obsługę dodatkowych urządzeń do logowania rozszerzonego, takich jak skanery ręczne. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją rozszerzania punktu sprzedaży.

<a name="using-extended-logon"></a>Używanie logowania rozszerzonego
====================

Jeśli logowanie rozszerzone jest skonfigurowane i pracownik ma przypisany kod kreskowy lub pasek magnetyczny, pracownik musi tylko przeciągnąć kartę magnetyczną w czytniku lub zeskanować kod kreskowy, gdy na ekranie wyświetlana jest strona logowania punktu sprzedaży. Jeśli logowanie wymaga podania hasła, wyświetla się również monit o podanie hasła.


