<section class="py-24 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto flex flex-col items-center">
    <h2 class="text-3xl sm:text-4xl font-bold text-center text-gray-900 mb-12 max-w-xl tracking-tight">
        Your miles tracked,<br />
        your achievements celebrated
    </h2>

    <div class="relative w-full max-w-2xl">
        <!-- Mock Achievement Card -->
        <div class="bg-white rounded-xl shadow-sm border border-gray-200 p-4 flex items-center gap-4">
            <div class="w-10 h-10 rounded-full bg-primary-100 overflow-hidden flex-shrink-0 flex items-center justify-center">
                <span class="text-2xl">🏆</span>
            </div>
            <div class="flex-1 min-w-0">
                <div class="flex items-center gap-2 mb-0.5">
                    <span class="font-semibold text-gray-900 truncate">500,000 Miles Milestone Achieved</span>
                </div>
                <div class="flex items-center gap-2 text-sm text-gray-500">
                    <span class="font-medium text-gray-900">This Week</span>
                    <span class="truncate">You're now ranked #847 nationally. Keep pushing!</span>
                </div>
            </div>
            <div class="flex-shrink-0">
                <span class="inline-flex items-center gap-1 px-2 py-1 rounded-full bg-primary-50 border border-primary-200 text-xs font-medium text-primary-600">
                    <svg class="w-3 h-3 text-primary-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
                    Milestone
                </span>
            </div>
        </div>

        <!-- Hand drawn arrow and text -->
        <div class="absolute -bottom-16 left-1/2 -translate-x-1/2 flex flex-col items-center">
             <div class="relative">
                <svg width="120" height="60" viewBox="0 0 120 60" fill="none" class="text-gray-300 transform rotate-12">
                    <path d="M10,50 Q60,60 110,10" stroke="currentColor" stroke-width="2" fill="none" marker-end="url(#arrowhead)" />
                    <defs>
                        <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
                        <polygon points="0 0, 10 3.5, 0 7" fill="currentColor" />
                        </marker>
                    </defs>
                </svg>
                <span class="absolute top-8 left-1/2 -translate-x-1/2 text-gray-400 font-handwriting text-sm whitespace-nowrap font-serif italic">Automatic tracking</span>
            </div>
        </div>
    </div>
</section>
