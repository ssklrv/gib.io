# gib.io
export default function OnlinePlannerTemplate() {
  const days = ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс'];

  const events = {
    2: ['Учёба 10:00 🐾'],
    4: ['Встреча 💕'],
    8: ['Тренировка'],
    10: ['Проект'],
    15: ['Чтение 📚'],
    17: ['Дедлайн ✨'],
    24: ['День для себя 🌸'],
    29: ['Маникюр 💅'],
  };

  const catEmojis = ['🐱', '🐾', '🎀', '💖'];

  return (
    <div className="min-h-screen bg-gradient-to-br from-pink-100 via-rose-50 to-pink-200 p-6 text-rose-900">
      <div className="max-w-7xl mx-auto">
        <div className="bg-white/70 backdrop-blur-xl rounded-[40px] shadow-2xl border border-pink-200 overflow-hidden">
          <div className="grid lg:grid-cols-[260px_1fr_320px] gap-0">

            <aside className="bg-pink-50 border-r border-pink-100 p-6 flex flex-col justify-between">
              <div>
                <div className="bg-pink-100 rounded-3xl p-5 text-center shadow-sm mb-8">
                  <div className="text-7xl mb-2">🐱</div>
                  <h1 className="text-3xl font-bold text-rose-700">Твой планер</h1>
                  <p className="text-rose-400 mt-2 text-sm">
                    Планируй, мечтай и отдыхай ✨
                  </p>
                </div>

                <nav className="space-y-3">
                  {[
                    '📅 Календарь',
                    '💖 Задачи',
                    '📝 Заметки',
                    '🎯 Цели',
                    '🌸 Привычки',
                    '☁️ Настроение',
                  ].map((item) => (
                    <button
                      key={item}
                      className="w-full text-left px-5 py-4 rounded-2xl bg-white hover:bg-pink-100 transition shadow-sm border border-pink-100"
                    >
                      {item}
                    </button>
                  ))}
                </nav>
              </div>

              <div className="bg-white rounded-3xl p-5 border border-pink-100 shadow-sm mt-8 text-center">
                <div className="text-5xl mb-3">😺</div>
                <p className="text-sm text-rose-500 leading-relaxed">
                  Не забывай отдыхать и заботиться о себе 💕
                </p>
              </div>
            </aside>

            <main className="p-6 lg:p-8">
              <div className="flex flex-col md:flex-row md:items-center md:justify-between gap-4 mb-6">
                <div>
                  <p className="text-rose-400 mb-2">Привет, солнышко 🌸</p>
                  <h2 className="text-4xl font-bold text-rose-700">
                    Май 2026
                  </h2>
                </div>

                <div className="flex gap-3 flex-wrap">
                  <button className="bg-white px-5 py-3 rounded-2xl border border-pink-200 shadow-sm hover:scale-105 transition">
                    ← Назад
                  </button>
                  <button className="bg-pink-300 text-white px-5 py-3 rounded-2xl shadow hover:scale-105 transition">
                    Сегодня
                  </button>
                  <button className="bg-white px-5 py-3 rounded-2xl border border-pink-200 shadow-sm hover:scale-105 transition">
                    Вперёд →
                  </button>
                </div>
              </div>

              <div className="bg-white rounded-[32px] border border-pink-100 overflow-hidden shadow-lg">
                <div className="grid grid-cols-7 bg-pink-50 border-b border-pink-100">
                  {days.map((day) => (
                    <div
                      key={day}
                      className="text-center py-4 font-semibold text-rose-500"
                    >
                      {day}
                    </div>
                  ))}
                </div>

                <div className="grid grid-cols-7 auto-rows-[140px]">
                  {Array.from({ length: 35 }, (_, index) => {
                    const date = index + 1;
                    const hasEvent = events[date];
                    const randomEmoji = catEmojis[index % catEmojis.length];

                    return (
                      <div
                        key={date}
                        className="border border-pink-50 p-3 relative hover:bg-pink-50/60 transition"
                      >
                        {date <= 31 && (
                          <>
                            <div className="flex justify-between items-center mb-3">
                              <span className="font-semibold text-rose-500">
                                {date}
                              </span>

                              {date === 15 && (
                                <span className="bg-pink-300 text-white text-xs px-2 py-1 rounded-full">
                                  Сегодня
                                </span>
                              )}
                            </div>

                            <div className="space-y-2">
                              {hasEvent?.map((event, idx) => (
                                <div
                                  key={idx}
                                  className="bg-pink-100 text-rose-700 text-xs px-3 py-2 rounded-2xl shadow-sm"
                                >
                                  {event}
                                </div>
                              ))}
                            </div>

                            {(date === 3 ||
                              date === 12 ||
                              date === 18 ||
                              date === 30) && (
                              <div className="absolute bottom-3 right-3 text-2xl opacity-70">
                                🐱
                              </div>
                            )}

                            <div className="absolute top-3 right-3 text-xs opacity-40">
                              {randomEmoji}
                            </div>
                          </>
                        )}
                      </div>
                    );
                  })}
                </div>
              </div>

              <div className="grid md:grid-cols-2 gap-6 mt-6">
                <div className="bg-white rounded-[30px] p-6 shadow-lg border border-pink-100">
                  <h3 className="text-2xl font-bold text-rose-700 mb-4">
                    🐾 План на сегодня
                  </h3>

                  <div className="space-y-4 text-sm">
                    {[
                      '08:00 Подъём и зарядка',
                      '10:00 Учёба',
                      '14:00 Работа над проектом',
                      '18:00 Тренировка',
                      '22:00 Отдых и сериал ✨',
                    ].map((task) => (
                      <div
                        key={task}
                        className="flex items-center justify-between bg-pink-50 px-4 py-3 rounded-2xl"
                      >
                        <span>{task}</span>
                        <span>💖</span>
                      </div>
                    ))}
                  </div>
                </div>

                <div className="bg-white rounded-[30px] p-6 shadow-lg border border-pink-100">
                  <h3 className="text-2xl font-bold text-rose-700 mb-4">
                    🎀 Заметки
                  </h3>

                  <textarea
                    placeholder="Запиши свои мысли..."
                    className="w-full h-64 bg-pink-50 border border-pink-100 rounded-3xl p-5 resize-none focus:outline-none focus:ring-2 focus:ring-pink-300"
                  />
                </div>
              </div>
            </main>

            <aside className="bg-rose-50 border-l border-pink-100 p-6 flex flex-col gap-6">
              <div className="bg-white rounded-[30px] p-5 shadow-sm border border-pink-100">
                <div className="flex items-center justify-between mb-4">
                  <h3 className="text-xl font-bold text-rose-700">
                    💖 Мои задачи
                  </h3>
                  <span className="text-3xl">🐱</span>
                </div>

                <div className="space-y-4 text-sm">
                  {[
                    'Подготовиться к экзамену',
                    'Купить подарки',
                    'Прочитать книгу',
                    'Разобрать фото',
                  ].map((task) => (
                    <label
                      key={task}
                      className="flex items-center gap-3 bg-pink-50 p-3 rounded-2xl"
                    >
                      <input type="checkbox" className="accent-pink-400" />
                      <span>{task}</span>
                    </label>
                  ))}
                </div>
              </div>

              <div className="bg-white rounded-[30px] p-5 shadow-sm border border-pink-100 text-center">
                <div className="text-6xl mb-3">📦🐱</div>
                <p className="text-rose-500 font-medium leading-relaxed">
                  Ты молодец! Горжусь тобой 💕
                </p>
              </div>

              <div className="bg-white rounded-[30px] p-5 shadow-sm border border-pink-100">
                <h3 className="text-xl font-bold text-rose-700 mb-4">
                  📊 Статистика
                </h3>

                <div className="space-y-5">
                  {[
                    ['Задачи выполнены', '75%'],
                    ['Продуктивность', '82%'],
                    ['Привычки', '6/7'],
                  ].map(([title, value]) => (
                    <div key={title}>
                      <div className="flex justify-between text-sm mb-2">
                        <span>{title}</span>
                        <span>{value}</span>
                      </div>

                      <div className="w-full bg-pink-100 rounded-full h-3 overflow-hidden">
                        <div className="bg-pink-400 h-3 rounded-full w-3/4" />
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            </aside>
          </div>
        </div>
      </div>
    </div>
  );
}
