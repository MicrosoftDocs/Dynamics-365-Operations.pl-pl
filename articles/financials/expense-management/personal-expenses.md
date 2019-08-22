---
title: Wydatki osobiste w raporcie wydatków
description: W tym temacie opisano dwie metody obsługi wydatków osobistych pracownika w Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b072fa9e78563d3e89b4d60e9ce61473902fee76
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2019
ms.locfileid: "1795004"
---
# <a name="personal-expenses-on-an-expense-report"></a>Wydatki osobiste w raporcie z wydatków

[!include [banner](../includes/banner.md)]

Podczas podróży służbowej pracownik może czasami obciążać firmową kartę kredytową swoimi osobistymi wydatkami. Jeśli nie zdefiniujesz procesu obsługi wydatków osobistych, proces zatwierdzania raportów z wydatków może zostać zakłócony, gdy pracownicy składają szczegółowe raporty z wydatków. 

W Microsoft Dynamics 365 for Finance and Operations dostępne są dwie metody obsługi wydatków osobistych pracownika:

- **Zapłacone przez pracownika etatowego** — organizacja nie pokrywa wydatków osobistych, które pojawiają się na wyciągu z konta firmowej karty kredytowej. Zamiast tego jest tworzony raport, który pokazuje wydatki osobiste wraz z wydatkami firmowymi obciążającymi firmową kartę kredytową.
- **Zapłacone przez firmę** — firma płaci całe saldo wyciągu z rachunku firmowej karty kredytowej, a następnie obciąża konto pracownika kwotą wydatków osobistych.

Metodę używaną przez organizację można zaznaczyć na stronie **Parametry zarządzania wydatkami**.
