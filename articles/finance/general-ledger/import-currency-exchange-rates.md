---
title: Importowanie kursów wymiany walut
description: Ten temat zawiera informacje o wymaganiach dotyczących importowania kursów referencyjnych dla walut obcych opublikowanych za pomocą bankowych kursów wymiany.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 74acfab28d45fc75c4ecd595aeba1fb1e13bbcff
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138085"
---
# <a name="import-currency-exchange-rates"></a>Importowanie kursów wymiany walut

[!include [banner](../includes/banner.md)]

Jeżeli firma otrzymała faktury w walutach obcych, jest konieczne przeliczenie tych walut na walutę lokalną. Oznacza to, że są potrzebne aktualne kursy wymiany różnych walut. Ten temat zawiera omówienie wymaganych ustawień i przetwarzania wymaganych do importowania referencyjnych kursów wymiany publikowanych w Internecie przez dostawców kursów wymiany, takich jak Europejski Bank Centralny i Bank Centralny Rosji.

W poniższych sekcjach opisano przepływ informacji używanych do konfigurowania i przetwarzania importu kursów wymiany walut.

## <a name="configure-an-exchange-rate-provider"></a>Konfigurowanie dostawcy kursów wymiany
Aby można było importować kursy wymiany walut, należy skonfigurować informacje wymagane przez dostawców oferujących kursy wymiany. Użyj strony **Konfigurowanie bankowych kursów wymiany**, aby wybrać dostawców kursu wymiany walut. Niektórzy dostawcy kursów wymiany są zawarci w danych demonstracyjnych w programie Dynamics 365 Finance. Poniższa tabela zawiera opisy formantów wspominanych na tej stronie.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Pole** | **Opis**                                                                                                                                                                                                             |
| **Nazwa**  | Nazwa bankowego kursu wymiany.                                                                                                                                                                                     |
| **Klucz**   | Unikatowy identyfikator informacji o poszczególnych konfiguracjach wymaganych przez dostawcę. Ta informacja jest automatycznie dodawana dla każdego dostawcy kursów wymiany dodanego przez użytkownika. |
| **Value** | Informacje dla każdego klucza. Ta informacja jest dodawana dla każdego dostawcy kursów wymiany dodanego przez użytkownika.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importowanie kursów wymiany walut
Można zaimportować kursy wymiany ze źródła dostawców kursów wymiany oraz dodać je na stronie **Kursy wymiany waluty**. Strona **Importowanie kursów wymiany walut** służy do importowania kursów wymiany. Poniższa tabela zawiera opisy pól, które są wymagane w celu pomyślnego wykonania procesu importu.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Pole**                              | **Opis**                                                                                                                                                                                                                                                                                                                                                             |
| **Typ kursu wymiany**                 | Typ kursu wymiany walut.                                                                                                                                                                                                                                                                                                                                                      |
| **Bankowy kurs wymiany**             | Dostawca kursów wymiany walut.                                                                                                                                                                                                                                                                                                                                                  |
| **Import od dnia**                       | Ten parametr określa, czy ma być importowany kurs z bieżącą datą, czy z konkretnego zakresu dat. Jeśli chcesz użyć zakresu dat, wprowadź lub wybierz daty początkową i końcową.                                                                                                                                                                                                                |
| **Utwórz wymagane pary walut**    | To pole wyboru decyduje o automatycznym tworzeniu par walut, jeśli jeszcze nie istnieją pary walut, które chcesz zaimportować. Ta opcja może być niedostępna dla niektórych dostawców.                                                                                                                                                                                               |
| **Zastąp istniejące kursy wymiany**   | To pole wyboru steruje aktualizacją istniejącego kursu wymiany dla pary walut, gdy kurs wymiany na określony dzień już istnieje. Jeśli to pole wyboru nie jest zaznaczone, kurs wymiany dla określonych dat nie jest importowany, jeśli istnieje już inny kurs wymiany.                                                                                       |
| **Zapobiegaj importowaniu w święto państwowe** | To pole wyboru steruje importem kursu wymiany z dnia ustawowo wolnego od pracy. Na przykład jeśli zaznaczysz to pole wyboru i używasz Europejskiego Banku Centralnego jako dostawcy kursu wymiany, system nie zaktualizuje kursu wymiany w święto państwowe respektowane przez bieżącą firmę. Ta opcja może być niedostępna dla niektórych dostawców. |
| **Kurs wymiany z poprzedniego dnia** | To pole wyboru jest dostępne po włączeniu funkcji **importowania EBC z bieżącą lub poprzednią datą** na stronie **Zarządzanie funkcjami**. To pole wyboru jest dostępne tylko w przypadku dostawcy — *Europejskiego Banku Centralnego*. To pole wyboru należy zaznaczyć, aby zaimportować kurs wymiany waluty opublikowany przez Europejski Bank Centralny w poprzednim dniu roboczym około godziny 16:00 CET. Domyślnie to pole wyboru jest zaznaczone. To pole wyboru należy wyczyścić, aby zaimportować kurs wymiany waluty opublikowany w tym samym dniu roboczym.  |
