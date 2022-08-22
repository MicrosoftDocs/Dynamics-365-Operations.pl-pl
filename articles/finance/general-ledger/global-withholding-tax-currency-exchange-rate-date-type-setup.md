---
title: Włącz konfigurację globalnej waluty potrąconej typ kursu wymiany potrąconej zaliczki na podatek i typu daty
description: W tym artykule opisano, jak włączyć globalne ustawienia waluty potrąconej zaliczki na podatek typ kursu wymiany typie daty.
author: kailiang
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 41f12a33651c14439f3a59c5c2f2d34019dada2d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229964"
---
# <a name="enable-the-global-withholding-tax-currency-exchange-rate-type-and-date-type-setup"></a>Włącz konfigurację globalnej waluty potrąconej typ kursu wymiany potrąconej zaliczki na podatek i typu daty

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

W tym artykule opisano, jak włączyć globalne ustawienia waluty potrąconej zaliczki na podatek typ kursu wymiany typie daty. Możesz teraz wybrać dedykowany typ kursu wymiany i typ daty obliczenia kursu wymiany dla waluty podatku u źródła. Te opcje określają kurs wymiany waluty obcej używany do obliczania kwoty podatku u źródła w walucie podatku u źródła w transakcjach płatniczych.

Ta funkcja jest dostępna w Microsoft Dynamics 365 Finance wersjach 10.0.29 i nowszych.

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Parametry** \> **Parametry księgi głównej**.
2. Na karcie **Potrącona zaliczka na podatek** ustaw opcję **Włącz walutę zaliczki na podatek** o wartości **Tak**.
3. W polu **Typ kursu wymiany** wybierz typ kursu wymiany dla waluty potrąconej zaliczki na podatek.
4. W polu **Typ daty obliczania** wybierz typ daty obliczania, który określa kurs wymiany waluty potrąconej zaliczki na podatek:

    - **Data płatności** — określa kurs wymiany na podstawie daty księgowania arkusza płatności.
    - **Data faktury** — Określ kurs wymiany na podstawie daty faktury arkusza faktur. Jeśli data faktury w załączniku jest pusta, zostanie użyta data księgowania faktury. 
    - **Data dokumentu** — Określ kurs wymiany na podstawie daty dokumentu arkusza płatności. Jeżeli data dokumentu vouchera jest pusta, zostanie użyta data płatności.

5. Wybierz opcję **Zapisz**.

Jeśli waluta transakcji różni się od waluty podatku u źródła zdefiniowanej w kodzie podatku u źródła, kwota w walucie podatku u źródła zostanie obliczona z waluty transakcji na podstawie poprzednich ustawień i zostanie zaksięgowana w zaksięgowanych transakcjach podatku u źródła.
