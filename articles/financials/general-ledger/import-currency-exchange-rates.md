---
title: Importowanie kursów wymiany walut
description: Jeżeli firma otrzymała faktury w walutach obcych, jest konieczne przeliczenie tych walut na walutę lokalną. Oznacza to, że są potrzebne aktualne kursy wymiany różnych walut. Ten temat zawiera omówienie wymaganych ustawień i przetwarzania importowania referencyjnych kursów wymiany publikowanych w Internecie przez dostawców kursów wymiany, takich jak Europejski Bank Centralny i Bank Centralny Rosji.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: edd72b48a640126577dd7a2add3a4891ae505fdf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557966"
---
# <a name="import-currency-exchange-rates"></a>Importowanie kursów wymiany walut

[!include [banner](../includes/banner.md)]

Jeżeli firma otrzymała faktury w walutach obcych, jest konieczne przeliczenie tych walut na walutę lokalną. Oznacza to, że są potrzebne aktualne kursy wymiany różnych walut. Ten temat zawiera omówienie wymaganych ustawień i przetwarzania importowania referencyjnych kursów wymiany publikowanych w Internecie przez dostawców kursów wymiany, takich jak Europejski Bank Centralny i Bank Centralny Rosji.

W poniższych sekcjach opisano przepływ informacji używanych do konfigurowania i przetwarzania importu kursów wymiany walut.

## <a name="configure-an-exchange-rate-provider"></a>Konfigurowanie dostawcy kursów wymiany
Aby można było importować kursy wymiany walut, należy skonfigurować informacje wymagane przez dostawców oferujących kursy wymiany. Użyj strony **Konfigurowanie bankowych kursów wymiany**, aby wybrać dostawców kursu wymiany walut. Niektórzy dostawcy kursów wymiany są zawarci w danych demonstracyjnych w programie Microsoft Dynamics 365 for Finance and Operations. Poniższa tabela zawiera opisy formantów wspominanych na tej stronie.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Pole** | **Opis**                                                                                                                                                                                                             |
| **Nazwa**  | Nazwa bankowego kursu wymiany.                                                                                                                                                                                     |
| **Klucz**   | Unikatowy identyfikator informacji o poszczególnych konfiguracjach wymaganych przez dostawcę. Ta informacja jest automatycznie dodawana dla każdego dostawcy kursów wymiany dodawanego przez kliknięcie przycisku **Dodaj**. |
| **Wartość** | Informacje dla każdego klucza. Ta informacja jest dodawana dla każdego dostawcy kursów wymiany dodawanego przez kliknięcie przycisku **Dodaj**.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importowanie kursów wymiany walut
Można zaimportować kursy wymiany ze źródła dostawców kursów wymiany oraz ustawić je na stronie **Kursy wymiany waluty**. Strona **Importowanie kursów wymiany walut** służy do importowania kursów wymiany. Poniższa tabela zawiera opisy pól, które są wymagane w celu pomyślnego wykonania procesu importu.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Pole**                              | **Opis**                                                                                                                                                                                                                                                                                                                                                             |
| **Typ kursu wymiany**                 | Typ kursu wymiany walut.                                                                                                                                                                                                                                                                                                                                                      |
| **Bankowy kurs wymiany**             | Dostawca kursów wymiany walut.                                                                                                                                                                                                                                                                                                                                                  |
| **Import od dnia**                       | Ten parametr określa, czy ma być importowany kurs z dzisiaj, czy z zakresu dat. Jeśli chcesz użyć zakresu dat, wprowadź lub wybierz daty początkową i końcową.                                                                                                                                                                                                                |
| **Utwórz wymagane pary walut**    | To pole wyboru decyduje o automatycznym tworzeniu par walut, jeśli jeszcze nie istnieją pary walut, które chcesz zaimportować. Ta opcja może być niedostępna dla niektórych dostawców.                                                                                                                                                                                               |
| **Zastąp istniejące kursy wymiany**   | To pole wyboru steruje aktualizacją istniejącego kursu wymiany dla pary walut, gdy kurs wymiany na określony dzień już istnieje. Jeśli to pole wyboru nie jest zaznaczone, kurs wymiany dla określonych dat nie jest importowany, jeśli istnieje już inny kurs wymiany.                                                                                       |
| **Zapobiegaj importowaniu w święto państwowe** | To pole wyboru steruje importem kursu wymiany z dnia ustawowo wolnego od pracy. Na przykład jeśli zaznaczysz to pole wyboru i używasz Europejskiego Banku Centralnego jako dostawcy kursu wymiany, system nie zaktualizuje kursu wymiany w święto państwowe respektowane przez bieżącą firmę. Ta opcja może być niedostępna dla niektórych dostawców. |





