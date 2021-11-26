---
title: Parametry międzyfirmowe
description: W tym temacie wyjaśniono parametry międzyfirmowe
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: face3cbd21998edcba528548ec4ae52354330aa3
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778504"
---
# <a name="intercompany-parameters"></a>Parametry międzyfirmowe

[!include [banner](../../includes/banner.md)]

W organizacji międzyfirmowej można skonfigurować parametry określające sposób handlu między różnymi podmiotami prawnymi. Te parametry są określone przez wybrane pola. Możesz wybrać różne kombinacje, aby odzwierciedlić różne scenariusze handlowe.

Poniższe dwa przykłady opisują scenariusze dla organizacji międzyfirmowych, jeden z dwoma poziomami i jeden z trzema poziomami.

## <a name="example-1-two-level-intercompany-chain"></a>Przykład 1: Dwupoziomowy łańcuch międzyfirmowy

Organizacja międzyfirmowa obejmuje następujące osoby prawne:

- Firma A – sprzedaje do odbiorców zewnętrznych, ale nie ma zapasów. Ta firma kupuje od firmy B.
- Firma B — sprzedaż tylko firmie A.

Obie firmy mogą sprzedawać i kupować od siebie.

W tym przykładzie wycena pierwotnego zamówienia sprzedaży, które jest kierowane do klienta zewnętrznego, jest zawsze oparta na cenie sprzedaży. Ceny na międzyfirmowym zamówieniu sprzedaży i międzyfirmowym zamówieniu zakupu są uzależnione od wewnętrznej ceny sprzedaży/ceny transferowej na międzyfirmowym zamówieniu sprzedaży w wewnętrznej firmie sprzedającej B.

Informacje zawarte w nagłówku zamówienia są uzależnione od informacji zawartych na oryginalnym zamówieniu sprzedaży odbiorcy zewnętrznego. Zmiany na międzyfirmowym zamówieniu sprzedaży nie są zsynchronizowane z oryginalnym zamówieniem sprzedaży.

Na stronie Firma A na stronie **Międzyfirmowe** dla dostawców wybierz pozycję **Zasady zamówienia zakupu**. W grupie pól **Oryginalne zamówienie sprzedaży (dostawa bezpośrednia)** należy wybrać następujące pola:

- **Drukuj dokument dostawy automatycznie**
- **Księguj fakturę automatycznie**
- **Drukuj fakturę automatycznie**

W grupie pól **Międzyfirmowe zamówienie zakupu (dostawa bezpośrednia)** wybierz następujące pole:

- **Księguj fakturę automatycznie**

W grupie pól **Oryginalne zamówienie sprzedaży <-> Międzyfirmowe zamówienie zakupu** wybierz następujące pole:

- **Informacje o odbiorcy**
- **Numer w bazie Chemical Abstracts Service (RMA)**

W grupie pól **Międzyfirmowe zamówienie zakupu <-> Międzyfirmowe zamówienie sprzedaży** wybierz następujące pole:

- **Informacje o odbiorcy**
- **Numer w bazie Chemical Abstracts Service (RMA)**
- **Numer partii**
- **Numer seryjny**

Na stronie Firma B na stronie **Międzyfirmowe** dla klientów wybierz pozycję **Zasady zamówień sprzedaży**. W grupie pól **Tworzenie międzyfirmowych zamówień sprzedaży** należy wybrać następujące pola:

- **Numerowanie zamówień sprzedaży**: **firma + numer oryginalny**
- **Zezwalaj na aktualizację zbiorczą dokumentów dla oryginalnego odbiorcy**

W grupie pól **Ceny międzyfirmowych zamówień sprzedaży** należy wybrać następujące pola:

- **Wyszukiwanie ceny i rabatu**
- **Zezwalaj na edycję ceny**
- **Zezwalaj na edycję rabatu**

W grupie pól **Międzyfirmowe zamówienie sprzedaży \> Międzyfirmowe zamówienie zakupu** wybierz następujące pole:

- **Numer partii**
- **Numer seryjny**

## <a name="example-2-three-level-intercompany-chain"></a>Przykład 2: trzypoziomowy łańcuch międzyfirmowy

Organizacja międzyfirmowa obejmuje następujące osoby prawne:

- Firma A – firma sprzedana klientom zewnętrznym i kupowana od firmy B.
- Firma B – firma produkcyjna lub dystrybucyjna, która nie może dostarczać produktów ani kupować od firmy C.
- Firma C – firma zajmująca się produkcją lub dystrybucją, która dostarcza produkty do firmy B.

Wewnętrzne ceny transferowe między podmiotami prawnymi B i C są ponoszone przez sprzedającą osobę prawną na początku łańcucha. Jest to również koszt firmy A, która sprzedaje do odbiorców zewnętrznych. Jednak wycena pierwotnego zamówienia sprzedaży dla klienta zewnętrznego jest zawsze oparta na cenie sprzedaży.

Ceny wszystkich międzyfirmowych zamówień sprzedaży i międzyfirmowych zamówień zakupu są kontrolowane na podstawie międzyfirmowego zamówienia sprzedaży. Jest on kontrolowany na początku łańcucha. Dlatego cenę kontroluje firma C, która sprzedaje firmie B. Ceny międzyfirmowych zamówień sprzedaży są oparte na wewnętrznej sprzedaży lub cenach transferowych skonfigurowanych w firmie C.

Informacje zawarte w nagłówku zamówienia są uzależnione od informacji zawartych na oryginalnym zamówieniu sprzedaży odbiorcy zewnętrznego. Zmiany na międzyfirmowym zamówieniu nie są zsynchronizowane z oryginalnym zamówieniem sprzedaży.

Należy wybrać następujące parametry:

Na stronie Firma A na stronie **Międzyfirmowe** dla dostawców wybierz pozycję **Zasady zamówienia zakupu**. W grupie pól **Oryginalne zamówienie sprzedaży (dostawa bezpośrednia)** należy wybrać następujące pola:

- **Drukuj dokument dostawy automatycznie**
- **Księguj fakturę automatycznie**
- **Drukuj fakturę automatycznie**

W grupie pól **Międzyfirmowe zamówienie zakupu (dostawa bezpośrednia)** wybierz następujące pole:

- **Księguj fakturę automatycznie**

W grupie pól **Oryginalne zamówienie sprzedaży <-> Międzyfirmowe zamówienie zakupu** wybierz następujące pole:

- **Informacje o odbiorcy**
- **Numer w bazie Chemical Abstracts Service (RMA)**

W grupie pól **Międzyfirmowe zamówienie zakupu <-> Międzyfirmowe zamówienie sprzedaży** wybierz następujące pole:

- **Informacje o odbiorcy**
- **Numer w bazie Chemical Abstracts Service (RMA)**
- **Numer partii**
- **Numer seryjny**

Na stronie Firma B na stronie **Międzyfirmowe** dla klientów wybierz pozycję **Zasady zamówień sprzedaży**. W grupie pól **Tworzenie międzyfirmowych zamówień sprzedaży** należy wybrać następujące pola:

- **Numerowanie zamówień sprzedaży**: **firma + numer oryginalny**
- **Zezwalaj na aktualizację zbiorczą dokumentów dla oryginalnego odbiorcy**

W grupie pól **Międzyfirmowe zamówienie sprzedaży \> Międzyfirmowe zamówienie zakupu** wybierz następujące pole:

- **Numer partii**
- **Numer seryjny**

W grupie pól **Księgowanie faktur dla klientów międzyfirmowych** należy wybrać następujące pola:

- **Cena jednostkowa jest równa kosztowi własnemu**
- **Inicjuj księgowanie oryginalnej faktury dla odbiorcy**

Na stronie Firma B na stronie **Międzyfirmowe** dla dostawców wybierz pozycję **Zasady zamówienia zakupu**. W grupie pól **Oryginalne zamówienie sprzedaży (dostawa bezpośrednia)** należy wybrać następujące pola:

- **Drukuj dokument dostawy automatycznie**
- **Księguj fakturę automatycznie**
- **Drukuj fakturę automatycznie**

W grupie pól **Międzyfirmowe zamówienie zakupu (dostawa bezpośrednia)** wybierz następujące pole:

- **Księguj fakturę automatycznie**

W grupie pól **Oryginalne zamówienie sprzedaży <-> Międzyfirmowe zamówienie zakupu** wybierz następujące pole:

- **Informacje o odbiorcy**
- **Numer w bazie Chemical Abstracts Service (RMA)**
- **Cena i rabat**

W grupie pól **Międzyfirmowe zamówienie zakupu <-> Międzyfirmowe zamówienie sprzedaży** wybierz następujące pole:

- **Informacje o odbiorcy**
- **Numer w bazie Chemical Abstracts Service (RMA)**
- **Numer partii**
- **Numer seryjny**

Na stronie Firma C na stronie **Międzyfirmowe** dla klientów wybierz pozycję **Zasady zamówień sprzedaży**. W grupie pól **Tworzenie międzyfirmowych zamówień sprzedaży** należy wybrać następujące pola:

- **Numerowanie zamówień sprzedaży**: **kod sekwencji numerów**
- **Zezwalaj na aktualizację zbiorczą dokumentów dla oryginalnego odbiorcy**

W grupie pól **Ceny międzyfirmowych zamówień sprzedaży** należy wybrać następujące pole:

- **Wyszukiwanie ceny i rabatu**

W grupie pól **Księgowanie faktur dla klientów międzyfirmowych** należy wybrać następujące pola:

- **Cena jednostkowa jest równa kosztowi własnemu**
- **Inicjuj księgowanie oryginalnej faktury dla odbiorcy**

W grupie pól **Międzyfirmowe zamówienie sprzedaży <-> Międzyfirmowe zamówienie zakupu** wybierz następujące pole:

- **Numer partii**
- **Numer seryjny**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
