---
title: Konfigurowanie grup księgowania dla podatku
description: Podatek jest obliczany i księgowany na kontach głównych określonych w grupach księgowania.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 15421da6f325dfee22a303e9fe83a0e72895fa08
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "308352"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Konfigurowanie grup księgowania dla podatku

[!include [task guide banner](../../includes/task-guide-banner.md)]

Podatek jest obliczany i księgowany na kontach głównych określonych w grupach księgowania. Grupy księgowania są dołączane do każdego kodu podatku. Można skonfigurować osobne grupy księgowania dla każdego kodu podatku, użyć jednej grupy księgowania dla wszystkich kodów podatku lub przypisać wiele grup księgowania do kodów podatków. To nagranie wykorzystuje firmę demonstracyjną DEMF. 

1. Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Grupy księgowania.
2. Kliknij przycisk Nowy.
3. W polu Grupa księgowania wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Podatek należny wybierz konto główne dla wychodzących podatków, które są płatne na rzecz urzędu skarbowego.
    * Podatki są zbierane w imieniu urzędu skarbowego przy sprzedaży opodatkowanych towarów i usług.  
6. W polu Podatek naliczony wybierz konto główne dla przychodzących podatków, które otrzymuje się z urzędu skarbowego.
    * Dostawcy pobierają podatki w imieniu urzędu skarbowego, kiedy kupujesz opodatkowane towary i usługi. To pole jest niedostępne, gdy na stronie Parametry księgi głównej zaznaczono opcję Zastosuj zasady opodatkowania dla podatku. Zamiast tego podatki płacone dostawcom są księgowane po stronie debetowej na tym samym koncie, co zakupy.   
7. W polu Wydatki podatku nienaliczonego wybierz konto główne dla księgowania podatków konsumpcyjnych podlegających odliczeniu, które nie zostały pobrane ani zgłoszone do urzędu skarbowego przez dostawców w ramach systemu odwróconego podatku PTU/HST stosowanego w UE.
    * Opcja Podatek nienaliczony musi zostać wybrana dla kodu podatku w grupie podatków, która jest używana w transakcji.  To pole jest niedostępne, gdy na stronie Parametry księgi głównej zaznaczono opcję Zastosuj zasady opodatkowania dla podatku.   
8. W polu Podatek nienaliczony należny wybierz konto główne do księgowania przychodzących podatków konsumpcyjnych, które są płatne na rzecz urzędu skarbowego.
    * Opcja Podatek nienaliczony musi zostać wybrana dla kodu podatku w grupie podatków, aby można było zaksięgować podatek konsumpcyjny. Jeśli w oknie Parametry księgi głównej zaznaczono opcję Zastosuj zasady opodatkowania dla podatku, kompensacja jest księgowana na koncie wydatków transakcji.   
9. W polu Konto rozliczeniowe wybierz konto główne, na którym będzie księgowane saldo netto kont księgowych określonych w polach Podatek nienaliczony należny i Podatek naliczony.
    * Saldo zostanie utworzone podczas rozliczania podatku i wykonywania zadania księgowania.  Jeśli urząd skarbowy za okres rozliczeniowy jest skojarzony z kontem dostawcy, saldo jest zamiast tego księgowane na koncie dostawcy.   
10. W polu Rabat gotówkowy dostawcy wybierz konto główne do księgowania rabatów gotówkowych dla kodów podatków skojarzonych z tą grupą księgowania.
    * To ustawienie jest opcjonalne i jeśli konto nie zostanie wprowadzone, będzie używane konto główne z kodów rabatów gotówkowych. Może być korzystne używanie różnych kont dla poszczególnych grup księgowania, jeśli w oknie Grupy podatków zaznaczono opcję Cofnij podatek od rabatu gotówkowego.  
11. W polu Rabat gotówkowy odbiorcy wybierz konto główne do księgowania rabatów gotówkowych dla kodów podatków skojarzonych z tą grupą księgowania.
    * To ustawienie jest opcjonalne i jeśli konto nie zostanie wprowadzone, będzie używane konto główne z kodów rabatów gotówkowych. Może być korzystne używanie różnych kont dla poszczególnych grup księgowania, jeśli w oknie Grupy podatków zaznaczono opcję Cofnij podatek od rabatu gotówkowego.  
12. Kliknij przycisk Zapisz.

