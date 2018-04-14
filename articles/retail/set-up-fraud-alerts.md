---
title: "Ustawianie alertów o oszustwie"
description: "W tym temacie wyjaśniono sposób konfigurowania reguł powiadomień dla działu obsługi klienta o potencjalnie fałszywych informacjach przy przetwarzaniu zamówień. Można zdefiniować określone kody, które będą używane do automatycznego lub ręcznego wstrzymania podejrzanych zamówień."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans, SysOperationTemplateForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f57cdb44d5ed3b078478cf47b74d1a79ba10323c
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-fraud-alerts"></a>Konfigurowanie alertów o oszustwie

[!INCLUDE [banner](includes/banner.md)]

W tym temacie opisano sposób ustawiania kryteriów i zasad w celu wstrzymania potencjalnie fałszywych zamówień sprzedaży w celu dalszego sprawdzenia. Funkcja wykrywania oszustw służy do określania prawidłowości informacji w zamówieniu sprzedaży. Jeżeli informacje w zamówieniu sprzedaży budzą wątpliwości na podstawie obowiązujących w organizacji kryteriów i zasad dotyczących oszustw, zamówienie może zostać wstrzymane w celu dalszego sprawdzenia przez administratora.

> [!NOTE]
> Tej funkcji można używać tylko z przetwarzaniem zamówień sprzedaży kanału Biuro obsługi rozwiązania Retail. 

Po zdefiniowaniu kanału Biuro obsługi należy ustawić opcję **Włącz kończenie zamówienia** na **Tak**. Po włączeniu kończenia zamówienia użytkownicy mogą wyświetlić podsumowanie zamówienia i kliknąć opcję **Prześlij**, aby sfinalizować zamówienie. Użytkownicy będą także mogli korzystać z opcji ręcznego wstrzymania fałszywego zamówienia sprzedaży w celu sprawdzenia. Zamówienia sprzedaży wprowadzone przez użytkownika Centrum obsługi są przetwarzane z użyciem zasad i kryteriów wykrywania oszustw podczas procesu przesyłania.

Istnieją dwa typy kryteriów wykrywania oszustw, które system wykorzysta do sprawdzenia, czy należy wstrzymać zamówienie w celu sprawdzenia, czy nie stanowi oszustwa:

-   **Reguły statyczne** wykorzystują określoną wartość, na przykład numer telefonu umieszczony na czarnej liście lub adres e-mail oznaczony jako znany z wcześniejszego wykorzystania do przeprowadzenia transakcji związanych z oszustwem. Na stronie **Fałszywe dane statyczne** można dodać fałszywe informacje ręcznie lub za pomocą importu danych i dołączyć do nich punktację. Jeżeli wykrywanie oszustwa jest włączone, każde wprowadzone zamówienie sprzedaży zostanie porównane z danymi statycznymi. Jeżeli dane zostaną znalezione w adresie fakturowania lub dostawy lub w adresie dostawy w wierszu sprzedaży, punktacja wszystkich unikatowych dopasowań zostanie zsumowana.  
-   **Reguły dynamiczne** składają się ze zmiennych i warunków zdefiniowanych dla tych zmiennych. Za pomocą reguł dynamicznych można sprawdzić inne kryteria niezdefiniowane w regułach statycznych. Bardziej złożone instrukcje „ORAZ/LUB” umożliwiają uwzględnienie wielu warunków do określenia, czy istnieje pozytywne dopasowanie względem kryteriów reguły i przesłanego zamówienia sprzedaży. Jeżeli na przykład użytkownik chce wstrzymać w celu sprawdzenia pod kątem oszustwa wszystkie zamówienia klientów związanych z określoną wartością grupy klientów i którzy zamówili określony produkt, warunki sprawdzenia poprawności klienta i produktów zostaną zdefiniowane na stronie **Reguły** z warunkiem „ORAZ”. Zamówienie zostanie wstrzymane tylko jako fałszywe tylko jeżeli oba warunki są prawdziwe, a wartość punktacji przypisana do reguły spowoduje ustawienie całkowitej punktacji zamówienia dotyczącej oszustwa powyżej wartości minimalnej zdefiniowanej w parametrach biura obsługi.

Użytkownik biura obsługi może także ręcznie dodać zamówienie do kolejki wstrzymania z powodu oszustwa. Jeżeli użytkownik wprowadzający zamówienie uważa, że klient składający zamówienie jest podejrzany i chce, aby inna osoba dodatkowo sprawdziła zamówienie przed przetworzeniem, użytkownik wprowadzający zamówienie może wybrać opcję **Ręczne wstrzymanie z powodu oszustwa** z listy rozwijanej **Wstrzymania** na stronie **Podsumowanie zamówienia sprzedaży** (wyświetlana po wywołaniu funkcji **Zakończ zamówienie**). Zostanie wyświetlony monit o wprowadzenie przez użytkownika notatki z dodatkowym wyjaśnienie dlaczego ich zdaniem zamówienie może być próbą oszustwa, aby osoba sprawdzająca miała dodatkowe informacje.

Wszystkie zamówienia wstrzymane za pomocą ręcznego wstrzymania z powodu oszustwa lub systematycznego obliczania punktacji dotyczącej oszustwa będą widoczne na stronie **Wstrzymania zamówień**, gdzie można sprawdzić zamówienie, a następnie anulować je lub zwolnić do przetwarzania.

> [!NOTE]
> Użycie wielu reguł lub zbyt złożonych reguł spowoduje ograniczenie wydajności systemu po przesłaniu zamówień sprzedaży. Funkcja alertów o oszustwie nie została zoptymalizowana do obsługi dużej liczby statycznych wpisów danych o oszustwach i wielu aktywnych reguł. Należy pamiętać, że każda reguła jest oceniana podczas przesyłania wpisu zamówienia sprzedaży biura obsługi. Te reguły są oceniane względem nagłówka zamówienia sprzedaży i wszystkich wierszy zamówień. Im więcej zasad i złożoność instrukcji reguły tym dłuższy czas przetwarzania. Jeżeli masz w zamówieniu dużą liczbę pozycji w wierszu, dużą liczbę aktywnych reguł i statycznych wpisów danych, systematyczny proces przeglądania i sprawdzania poprawności wszystkich danych i obliczania punktacji dotyczącej oszustwa może mieć duży wpływ na wydajność.  Organizacje korzystające z tej funkcji powinny zawsze przetestować i sprawdzić, czy czas przetwarzania przesyłania zamówień jest dopuszczalny przed zastosowaniem zmian w regułach lub statycznych kryteriach dotyczących oszustwa w środowisku produkcyjnym.

