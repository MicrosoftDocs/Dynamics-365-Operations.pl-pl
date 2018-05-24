---
title: "Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania faktur za umowy w programie Microsoft Dynamics 365 for Field Service z fakturami niezależnymi w programie Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: ace66c037953f4b1b2e8b93a315faefdb090b1eb
ms.openlocfilehash: 6672e283a5e56b068e3494d53a0fd6dd08253ba9
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a>Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania faktur za umowy w programie Microsoft Dynamics 365 for Field Service z fakturami niezależnymi w programie Microsoft Dynamics 365 for Finance and Operations.

## <a name="templates-and-tasks"></a>Szablony i zadania

Następujący szablon i podstawowe zadania są używane do wykonywania synchronizacji faktur za umowy w aplikacji Field Service z fakturami niezależnymi w aplikacji Finance and Operations.

**Nazwa szablonu w integracji danych:**

- Faktury za umowy (z Field Service do Fin and Ops)

**Nazwy zadań w projekcie integracji danych:**

- Nagłówki faktur
- Wiersze faktury

Następująca synchronizacja jest wymagana, zanim będzie można zsynchronizować faktury za umowy:

- Produkty (z Sales do Fin and Ops) — bezpośrednie

## <a name="entity-set"></a>Zestaw jednostek

| Field Service  | Finance and Operations                 |
|----------------|----------------------------------------|
| faktury       | Nagłówki faktur niezależnych dla odbiorców (usługa CDS) |
| invoicedetails | Wiersze faktur niezależnych dla odbiorców (usługa CDS)   |

## <a name="entity-flow"></a>Przepływ jednostek

Faktury tworzone na podstawie umowy w programie Field Service mogą być synchronizowane z programem Finance and Operations za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS). Aktualizacje tych faktur będą synchronizowane z fakturami niezależnymi w programie Finance and Operations, jeśli faktury niezależne mają stan księgowania **W trakcie przetwarzania**. Po zaksięgowaniu faktur niezależnych w programie Finance and Operations i zaktualizowaniu stanu księgowania na **Zakończone** nie będzie można synchronizować aktualizacji z programu Field Service.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service

Do jednostki **Faktury** dodano pole **Zawiera wiersze ze źródłem umowy**. To pole pomaga zagwarantować, że są synchronizowane tylko faktury utworzone na podstawie umowy. Wartością jest **prawda**, jeśli faktura zawiera co najmniej jeden wiersz faktury pochodzący z umowy.

Do jednostki **Wiersz faktury** dodano pole **Zawiera źródło umowy**. To pole pomaga zagwarantować, że są synchronizowane tylko wiersze faktur utworzone na podstawie umowy. Wartością jest **prawda**, jeżeli wiersz faktury pochodzi z umowy.

Pole **Data faktury** jest wymagane w aplikacji Finance and Operations. W związku z tym musi mieć wartość w programie Field Service, zanim będzie mogła nastąpić synchronizacja. Aby spełnić ten wymóg, dodano następującą logikę:

- Jeśli pole **Data faktury** jest puste w jednostce **Faktura** (tzn. jeśli nie ma wartości), jest w nim ustawiana bieżąca data podczas dodawania wiersza faktury pochodzącego z umowy.
- Użytkownik może zmienić wartość w polu **Data faktury**. Jednak gdy użytkownik próbuje zapisać fakturę pochodzącą z umowy, widzi błąd procesu biznesowego, jeśli pole **Data faktury** jest puste na fakturze.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

### <a name="in-finance-and-operations"></a>W programie Finance and Operations

Na potrzeby integracji należy skonfigurować pochodzenie faktury, tak aby w programie Finance and Operations odróżniać faktury niezależne utworzone na podstawie faktur za umowy w programie Field Service. Gdy faktura ma pochodzenie typu **Integracja faktury dotyczącej umowy**, pole **Zewnętrzny numer faktury** jest wyświetlane w nagłówku **Faktura sprzedaży**.

Informacje z pola **Zewnętrzny numer faktury** nie tylko pojawiają się w nagłówku faktury, ale mogą również pomóc zagwarantować, że faktury tworzone na podstawie faktur za umowy w programie Field Service są odfiltrowywane podczas synchronizacji faktur między programami Finance and Operations i Field Service.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Kody pochodzenia faktur**.
2. Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie faktury.
3. W polu **Pochodzenie faktury** nadaj nazwę pochodzeniu faktury, taką jak **FS**.
4. W polu **Opis** wprowadź opis, taki jak **Faktura za umowę w programie Field Service**.
5. Zaznacz pole wyboru **Przypisanie typu pochodzenia**.
6. W polu **Typ pochodzenia faktury** ustaw wartość **Integracja faktury dotyczącej umowy**.
7. Wybierz opcję **Zapisz**.

### <a name="in-the-data-integration-project"></a>W projekcie integracji danych

Zadanie: **Wiersze faktury**  

Upewnij się, że wartość domyślna pola **Wartość wyświetlana konta głównego** w programie Finance and Operations została zaktualizowana i jest zgodna z żądaną wartością.

Wartość domyślna w szablonie to **401100**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a>Faktury za umowy (z Field Service do Fin and Ops): Nagłówki faktur

[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a>Faktury za umowy (z Field Service do Fin and Ops): Wiersze faktur

[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)

