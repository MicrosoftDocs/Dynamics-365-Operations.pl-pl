---
title: "Importowanie kursów wymiany walut"
description: "Jeżeli podmiot prawny został faktur w walutach obcych, jest konieczne do konwersji waluty obcej w walucie lokalnej. Oznacza to, że wymagane są aktualne kursy wymiany walut. Ten temat zawiera omówienie wymagane ustawienia i przetwarzania importowania referencyjne kursy publikowane w Internecie przez dostawców kursu wymiany, takich jak Europejski Bank Centralny i Centralny Bank Rosji."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf66a1b1c9314b454223274810a21913d54b702d
ms.lasthandoff: 03/31/2017


---

# <a name="import-currency-exchange-rates"></a>Importowanie kursów wymiany walut

Jeżeli podmiot prawny został faktur w walutach obcych, jest konieczne do konwersji waluty obcej w walucie lokalnej. Oznacza to, że wymagane są aktualne kursy wymiany walut. Ten temat zawiera omówienie wymagane ustawienia i przetwarzania importowania referencyjne kursy publikowane w Internecie przez dostawców kursu wymiany, takich jak Europejski Bank Centralny i Centralny Bank Rosji.

W poniższych sekcjach opisano przepływu informacji, który jest używany do konfigurowania i przetwarzania importu kursów wymiany walut obcych.

## <a name="configure-an-exchange-rate-provider"></a>Konfigurowanie bankowy kurs wymiany
Przed zaimportowaniem kursów wymiany należy zdefiniować informacje wymagane przez dostawców, którzy oferują kursy wymiany. Użyj **Konfigurowanie bankowych kursów wymiany** strony, aby wybrać dostawców kursu wymiany. Niektórzy dostawcy kurs wymiany są dołączane do danych demonstracyjnych w usłudze Microsoft Dynamics 365 dla operacji. Poniższa tabela zawiera opisy formantów na tej stronie.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field** | **Description**                                                                                                                                                                                                             |
| **Name**  | Nazwa bankowego kursu wymiany.                                                                                                                                                                                     |
| **Klucz**   | Unikatowy identyfikator informacji o poszczególnych konfiguracjach wymaganych przez dostawcę. Informacja ta jest automatycznie dodawane dla każdego dostawcy kurs wymiany dodać po kliknięciu **Dodaj** przycisk. |
| **Value** | Informacje dla każdego klucza. Te informacje zostaną dodane dla każdego dostawcy kurs wymiany dodać po kliknięciu **Dodaj** przycisk.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importowanie kursów wymiany walut
Importowanie kursów wymiany z źródła dostawców kurs wymiany i ustawić je w **kursy wymiany walut** strony. Użyj **Importowanie kursów wymiany walut** stronę do importowania kursów wymiany. Poniższa tabela zawiera opisy pól, które są wymagane do ukończenia procesu importu.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Exchange rate type**                 | Typ kursu wymiany.                                                                                                                                                                                                                                                                                                                                                      |
| **Exchange rate provider**             | Dostawca kursu wymiany.                                                                                                                                                                                                                                                                                                                                                  |
| **Import as of**                       | Ten parametr umożliwia zarządzanie czy chcesz importować z dzisiejszą datą lub dla zakresu dat. Jeśli chcesz użyć zakresu dat, wprowadź lub wybierz daty rozpoczęcia i zakończenia.                                                                                                                                                                                                                |
| **Create necessary currency pairs**    | To pole wyboru zarządza automatyczne tworzenie pary walut, jeśli nie istnieją pary walut, które są importowane. Ta opcja może nie być dostępna dla niektórych dostawców.                                                                                                                                                                                               |
| **Override existing exchange rates**   | To pole wyboru zarządza aktualizację istniejącego kursu wymiany dla pary walut, kurs wymiany dla określonej daty już istnieje. Jeśli to pole wyboru nie jest zaznaczone, kurs wymiany dla określonej daty nie są importowane, jeśli istnieje już inny kurs wymiany.                                                                                       |
| **Prevent import on national holiday** | To pole wyboru umożliwia zarządzanie importu kursu wymiany z dnia, jest dniem ustawowo. Na przykład jeśli zaznaczenie tego pola wyboru i użyć Europejskiego Banku Centralnego jako dostawca kurs wymiany, system nie zaktualizuje kurs wymiany na Święto państwowe, która jest powiązana z bieżącej firmy. Ta opcja może nie być dostępna dla niektórych dostawców. |




