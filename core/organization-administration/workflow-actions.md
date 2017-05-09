---
title: "Akcje przepływu pracy"
description: "Ten artykuł wyjaśnia czynności, jakie może wykonywać każdy uczestnik procesu zatwierdzania w ramach przepływu pracy."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: adcb0443f5ad07ae7178e9fde963184951e6b8d9
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-actions"></a>Akcje przepływu pracy

[!include[banner](../includes/banner.md)]


Ten artykuł wyjaśnia czynności, jakie może wykonywać każdy uczestnik procesu zatwierdzania w ramach przepływu pracy.

Przepływ pracy może obejmować kilka grup osób: inicjatora, osoby przydzielone do zadań, osoby podejmujące decyzje i osoby zatwierdzające. Na przykład w następującym przepływie pracy raportów z wydatków Sam jest inicjatorem, osoby w kolejce są przypisane do zadania, John podejmuje decyzje, a Frank, Sue i Ann są osobami zatwierdzającymi.   [![Workflow\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif) W następującej części wyjaśniono działania w ramach przepływu pracy, które może wykonać każda grupa.

## <a name="actions-that-an-originator-can-perform"></a>Działania podejmowane przez inicjatora
Inicjator uruchamia wystąpienie przepływu pracy, przesyłając dokument do przetworzenia. Na przykład, Sam musi kliknąć przycisk **Prześlij** na stronie **Raport z wydatków**, aby przesłać jego raport z wydatków.

## <a name="actions-that-a-task-assignee-can-perform"></a>Akcje podejmowane przez osobę przydzieloną do zadania
Zadanie można przypisać do wielu osób lub do kolejki elementów roboczych, która jest monitorowana przez kilka osób. Jednak tylko jedna osoba może zakończyć zadanie. Na przykład Sam przesłał raport z wydatków i skierował pokwitowania do działu raportów z wydatków celem sprawdzenia. Członkowie działu raportów z wydatków Adventure Works monitorują kolejkę. Julie, członek tego działu, zaakceptował zadanie przeglądu raportu z wydatków i pokwitowań przesłanych przez Sama. Może teraz wykonać jedno z następujących działań: zakończyć, odrzucić, oddelegować, zażądać zmian, ponownie przypisać lub zwolnić. **Uwaga:** dostępne akcje będą się różnić, w zależności od sposobu zaprojektowania zadania przez programistę.

### <a name="complete"></a>Zakończenie

Zakończenie zadania przez użytkownika powoduje, że dokument przesłany do przetworzenia zostaje w razie potrzeby przypisany do następnego użytkownika w przepływie pracy, jeśli jest następny użytkownik. Jeśli dalsze przetwarzanie nie jest wymagane, proces przepływu pracy kończy się. Na przykład, Julie, członek działu raporty z wydatków Adventure Works, zaakceptowała zadanie przeglądu raportu z wydatków i pokwitowań przesłanych przez Sama. Po zakończeniu przeglądu dokument został przypisany do Johna.

### <a name="reject"></a>Odrzuć

Odrzucenie dokumentu przez użytkownika powoduje zakończenie procesu przepływu pracy. Na przykład, Julie, członek działu raporty z wydatków Adventure Works, zaakceptowała zadanie przeglądu raportu z wydatków i pokwitowań przesłanych przez Sama. Jeśli Julie odrzuci raport z wydatków, proces przepływu pracy zakończy się. Sam może następnie ponownie przesłać raport z wydatków. Może wprowadzić zmiany lub ponownie przesłać oryginalną wersję dokumentu. Jeśli Sam ponownie prześle raport, proces przepływu pracy rozpocznie się od nowa od zadania ręcznej kontroli.

### <a name="delegate"></a>Deleguj

Oddelegowanie zadania przez użytkownika powoduje, że zostaje ono przypisane do innego użytkownika. Na przykład, Julie, członek działu raporty z wydatków Adventure Works, zaakceptowała zadanie przeglądu raportu z wydatków i pokwitowań przesłanych przez Sama. Julie deleguje to zadanie do Timowi, który jest jej asystentem. Tim działa w imieniu Julie. Z tego względu po zakończeniu przeglądu przez Tima raport z wydatków zostaje przypisany do Johna, tak jakby to Julie zakończyła to zadanie.

### <a name="request-change"></a>Żądaj zmiany

Zażądanie przez użytkownika wprowadzenia zmian w przesłanym dokumencie powoduje, że dokument zostaje odesłany do inicjatora. Na przykład, Julie, członek działu raporty z wydatków Adventure Works, zaakceptowała zadanie przeglądu raportu z wydatków i pokwitowań przesłanych przez Sama. Julie zauważa kilka błędów w raporcie i prosi o wprowadzenie zmian. Raport z wydatków zostaje odesłany z powrotem do Sama. Sam może ponownie przesłać raport z wydatków. Może wprowadzić zmiany, o które prosiła Julie, lub ponownie przesłać oryginalną wersję dokumentu. Jeśli Sam ponownie prześle raport z wydatków, osoba z kolejki elementów roboczych musi jeszcze raz przejrzeć raport z wydatków i pokwitowania.

### <a name="reassign"></a>Przypisz ponownie

Osoby z kolejki elementów roboczych mogą ponownie przypisać dokumenty z kolejki do innej kolejki. Na przykład, Julie, członek zespołu raporty z wydatków Adventure Works, monitoruje kolejkę. Aby zrównoważyć obciążenie pracą, Julie może ponownie przypisać raport z wydatków i potwierdzenia do innej kolejki.

### <a name="release"></a>Zwolnienie

Może się tak zdarzyć, że jakaś osoba z kolejki elementów roboczych może zaakceptować zadanie, a następnie stwierdzić, że nie jest w stanie go wykonać. W takim przypadku osoba, która zaakceptowała zadanie, można zwolnić dokument z powrotem do kolejki elementów roboczych. Na przykład, Julie, członek działu raporty z wydatków Adventure Works, zaakceptowała zadanie przeglądu raportu z wydatków i pokwitowań przesłanych przez Sama. Jeśli Julie stwierdzi, że nie może wykonać zadania, może zwolnić dokument. Raport z wydatków zostanie zwrócony do kolejki, tak aby inni członkowie zespołu raporty z wydatków Adventure Works mogli zakończyć zadanie.

## <a name="actions-that-a-decision-maker-can-perform"></a>Działania podejmowane przez osobę podejmującą decyzje
Zazwyczaj dokument jest przypisany do osoby podejmującej decyzje, ponieważ jest pytanie, na które musi odpowiedzieć osoba podejmująca decyzję. Odpowiedź na pytanie brzmi zazwyczaj **Tak** lub **NIE**, albo **Prawda** lub **Fałsz**. Jeśli osoba podejmująca decyzję nie wybierze jednej z tych opcji, może delegować decyzję.

### <a name="choice-1-or-choice-2"></a>\[Wybór 1\] lub \[Wybór 2\]

Osoba podejmująca decyzję musi odpowiedzieć na pytanie związane z dokumentem. Odpowiedź na pytanie brzmi zazwyczaj **Tak** lub **NIE**, albo **Prawda** lub **Fałsz**. Odpowiedź wybrana przez osobę podejmującą decyzję wskazuje gałąź przepływu pracy, która zostanie użyta do przetworzenia dokumentu. Na przykład raport z wydatków Sama jest przypisany do Johna. John musi zdecydować, czy informacje zawarte w dokumencie wymagają skontaktowania się z przełożonym Sama. Jeśli John stwierdzi, że konieczne jest skontaktowanie się z przełożonym Sama, raport z wydatków zostaje przypisany do Arethy, która następnie musi skontaktować się z przełożonym Sama. Jeśli John stwierdzi, że nie ma potrzeby kontaktu z przełożonym Sama, raport z wydatków zostaje przypisany do Franka celem zatwierdzenia.

### <a name="delegate"></a>Deleguj

Jeśli osoba podejmująca decyzję oddelegowuje decyzję, dokument zostaje przypisany do innego użytkownika, który musi podjąć decyzję. Na przykład raport z wydatków Sama jest przypisany do Johna. John oddelegowuje decyzję do Marii, która jest jego asystentką. Następnie Maria działa w imieniu Johna. Jeśli Maria stwierdzi, że konieczne jest skontaktowanie się z przełożonym Sama, raport z wydatków zostaje przypisany do Arethy, która musi skontaktować się z przełożonym Sama. Jeśli Maria stwierdzi, że nie ma potrzeby kontaktu z przełożonym Sama, raport z wydatków zostaje przypisany do Franka celem zatwierdzenia.

## <a name="actions-that-an-approver-can-perform"></a>Działania podejmowane przez osobę zatwierdzającą
Po przypisaniu dokumentu do osoby zatwierdzającej może ona podjąć jedno z następujących działań: zatwierdzić, odrzucić, delegować lub poprosić o wprowadzenie zmian.

### <a name="approve"></a>Zatwierdzenie

Zatwierdzenie dokumentu przez osobę zatwierdzającą powoduje, że dokument zostaje przypisany do następnego użytkownika w przepływie pracy, o ile jest następny użytkownik. Jeśli dalsze przetwarzanie nie jest wymagane, proces przepływu pracy kończy się. Na przykład Sam przesłał raport z wydatków na kwotę 6000 USD, a ten dokument jest przypisany do Franka. Gdy Frank zatwierdzi dokument, zostanie on przypisany do Sue w celu zatwierdzenia. Gdy Sue zatwierdzi raport z wydatków, proces przepływu pracy zakończy się.

### <a name="reject"></a>Odrzuć

Odrzucenie dokumentu przez osobę zatwierdzającą powoduje zakończenie procesu przepływu pracy. Na przykład Sam przesłał raport z wydatków na kwotę 12 000 USD, a ten dokument jest przypisany do Sue. Jeśli Sue odrzuci raport, proces przepływu pracy zakończy się. Sam może ponownie przesłać raport z wydatków. Może najpierw wprowadzić zmiany lub ponownie przesłać oryginalną wersję raportu z wydatków. Jeśli Sue ponownie prześle raport, proces przepływu pracy rozpocznie się od nowa od procesu zatwierdzenia.

### <a name="delegate"></a>Deleguj

Oddelegowanie dokumentu przez osobę zatwierdzającą powoduje, że zostaje on przypisany do innego użytkownika w celu zatwierdzenia. Na przykład Sam przesłał raport z wydatków na kwotę 12 000 USD, a ten dokument jest przypisany do Franka. Wojciech deleguje raport do Anny. Ann będzie działać w imieniu Franka. Oznacza to, że po zatwierdzeniu przez Ann dokument zostanie przypisany do Sue w celu zatwierdzenia — tak jakby zatwierdził go Frank. Po zatwierdzeniu przez Sue dokument zostanie przesłany do Ann w celu zatwierdzenia.

### <a name="request-change"></a>Żądaj zmiany

Zażądanie przez osobę zatwierdzającą wprowadzenia zmian w dokumencie powoduje, że dokument zostaje odesłany do inicjatora. Na przykład Sam przesłał raport z wydatków na kwotę 12 000 USD, a ten dokument jest przypisany do Sue. Jeśli Sue poprosi o wprowadzenie zmian, raport z wydatków jest wysyłany z powrotem do Sama. Sam może ponownie przesłać raport z wydatków. Może on najpierw wprowadzić żądane zmiany lub ponownie przesłać oryginalną wersję raportu z wydatków. Jeśli Sam ponownie prześle raport, zostanie on wysłany do zatwierdzenia do Franka, ponieważ Frank jest pierwszą osobą zatwierdzającą w procesie zatwierdzania.




