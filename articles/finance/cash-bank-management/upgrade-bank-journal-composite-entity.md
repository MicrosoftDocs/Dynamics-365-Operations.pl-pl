---
title: Aktualizowanie jednostki złożonej arkusza bankowego
description: Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 974d6b3b11df92debdec26860fd9eea00a9f2313
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188034"
---
# <a name="update-the-bank-journal-composite-entity"></a>Aktualizowanie jednostki złożonej arkusza bankowego

[!include [banner](../includes/banner.md)]

Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.

Poniższa procedura umożliwia wstawienie dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.

1.  Skompiluj i zsynchronizuj następujące jednostki złożone, jednostki i tabele tymczasowe w arkuszu bankowym:
    -   Jednostka złożona\\BankJournalEntity
    -   Jednostka\\BankJournalHeaderEntity
    -   Jednostka\\BankJournalLineEntity
    -   Tabela\\BankJournalHeaderStaging
    -   Tabela\\BankJournalLineStaging

2.  Zarządzanie danymi\\projekty danych
    -   Udostępnij typ **Transakcja bankowa** w układzie **Dane źródłowe**.
        -   Format danych źródłowych = Element XML
        -   Nazwa jednostki = Arkusz bankowy
        -   Przekaż plik danych = nowa wersja pliku SampleBankJournalCompositeEntity.xml.
        -   Kliknij przycisk **Tak**, aby zastąpić istniejący plik.
        -   Kliknij przycisk **Tak**, aby wygenerować mapowanie od zera.
        -   Sprawdź, czy typ transakcji bankowej jest mapowany.
            -   W jednostce Wiersz kliknij opcję **Wyświetl mapę**.
            -   Upewnij się, że typ transakcji bankowej jest mapowany z obszaru Źródło do obszaru Tymczasowy.

3.  Zaimportuj nowy wyciąg.




