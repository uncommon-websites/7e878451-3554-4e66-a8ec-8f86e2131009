<script lang="ts">
    // Mock data for the interface
    const favorites = [
        { name: "My Stats", icon: "chart" },
        { name: "Top Drivers", icon: "trophy" },
        { name: "Achievements", icon: "star" },
        { name: "Weekly Challenge", icon: "doc" }
    ];

    const channels = [
        { name: "National Leaderboard", icon: "trophy", color: "bg-primary-100 text-primary-600" },
        { name: "Regional Rankings", icon: "hash", color: "bg-yellow-100 text-yellow-600" },
        { name: "Safety Champions", icon: "shield", color: "bg-blue-100 text-blue-600" },
        { name: "Million Mile Club", icon: "star", color: "bg-purple-100 text-purple-600" },
        { name: "Fuel Efficiency", icon: "hash", color: "bg-green-100 text-green-600" },
        { name: "Long Haul Legends", icon: "hash", color: "bg-orange-100 text-orange-600" },
        { name: "Team Challenges", icon: "hash", color: "bg-indigo-100 text-indigo-600" },
        { name: "Route Masters", icon: "hash", color: "bg-cyan-100 text-cyan-600" },
        { name: "Weekly Winners", icon: "hash", color: "bg-pink-100 text-pink-600" },
        { name: "Driver Community", icon: "hash", color: "bg-gray-100 text-gray-600" }
    ];

    const posts = [
        {
            title: "🏆 Mike 'Roadking' Johnson hit 1 million miles!",
            author: "Achievement Unlocked",
            preview: "Joined the exclusive Million Mile Club. 15 years of safe driving!",
            tag: "Million Mile",
            tagColor: "text-purple-500",
            icon: "👑",
            iconBg: "bg-primary-600"
        },
        {
            title: "You moved up 12 spots on the National Leaderboard",
            author: "Leaderboard Update",
            preview: "Great week! You're now ranked #847 nationally with 2,847 miles this week.",
            tag: "Rankings",
            tagColor: "text-blue-500",
            icon: "📈",
            iconBg: "bg-gray-100"
        },
        {
            title: "Weekly Challenge: Coast-to-Coast Sprint",
            author: "Challenge Active",
            preview: "3,200 miles in 6 days. 847 drivers competing. You're in 23rd place!",
            tag: "Challenge",
            tagColor: "text-primary-500",
            icon: "🎯",
            iconBg: "bg-white border"
        },
        {
            title: "Safety Streak: 90 Days Incident-Free",
            author: "Safety Achievement",
            preview: "Keep it up! You're on track for the Quarterly Safety Champion badge.",
            tag: "Safety",
            tagColor: "text-green-500",
            icon: "🛡️",
            iconBg: "bg-white border"
        }
    ];

    const yesterdayPosts = [
        {
            title: "Sarah 'Highway Queen' Martinez: 500K Miles",
            author: "Achievement Unlocked",
            preview: "Halfway to the Million Mile Club! Averaging 2,500 miles/week for 4 years straight.",
            tag: "Milestone",
            tagColor: "text-pink-500",
            icon: "⭐",
            iconBg: "bg-primary-600 text-white"
        },
        {
            title: "Regional Rankings Updated: Southwest Division",
            author: "Leaderboard Update",
            preview: "Top 10 shuffled! Check your new position and see who's gaining on you.",
            tag: "Rankings",
            tagColor: "text-indigo-500",
            icon: "📊",
            iconBg: "bg-indigo-600 text-white"
        },
        {
            title: "New Badge Earned: Night Owl (100 overnight hauls)",
            author: "Badge System",
            preview: "You've completed 100 overnight long-haul trips. Elite driver status!",
            tag: "Badge",
            tagColor: "text-yellow-500",
            icon: "🦉",
            iconBg: "bg-yellow-100"
        }
    ];

    const team = [
        { name: "Mike 'Roadking' J.", status: "On the road", online: true, img: "https://i.pravatar.cc/150?u=mike", rank: "#1" },
        { name: "Sarah 'Highway Queen' M.", status: "Loading", online: true, img: "https://i.pravatar.cc/150?u=sarah", rank: "#2" },
        { name: "Tommy 'Iron Horse' R.", online: true, img: "https://i.pravatar.cc/150?u=tommy", rank: "#3" },
        { name: "Lisa 'Mile Master' K.", online: true, img: "https://i.pravatar.cc/150?u=lisa", rank: "#4" },
        { name: "Carlos 'El Camino' D.", online: true, img: "https://i.pravatar.cc/150?u=carlos", rank: "#5" },
        { name: "Jake 'Diesel' P.", online: false, img: "https://i.pravatar.cc/150?u=jake", rank: "#6" }
    ];
</script>

<div class="rounded-xl border border-gray-200 bg-white shadow-2xl overflow-hidden flex h-[800px] text-sm select-none relative z-10">
    <!-- Left Sidebar -->
    <div class="w-64 bg-gray-50 border-r border-gray-200 flex flex-col flex-shrink-0">
        <!-- Header -->
        <div class="p-3 border-b border-gray-200 flex items-center justify-between">
            <div class="flex items-center gap-2 font-medium text-gray-900">
                <div class="w-5 h-5 bg-primary-600 rounded flex items-center justify-center text-white text-xs font-bold">H</div>
                HONK!
                <svg class="w-3 h-3 text-gray-400" viewBox="0 0 16 16" fill="currentColor"><path d="M4 6l4 4 4-4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </div>
            <div class="flex items-center gap-1">
                 <svg class="w-4 h-4 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 8v8M8 12h8"/></svg>
            </div>
        </div>

        <!-- New Trip Button -->
        <div class="px-3 py-2">
            <button class="w-full bg-white border border-gray-200 rounded-md py-1.5 px-3 text-gray-600 font-medium text-left shadow-sm flex items-center gap-2 hover:bg-gray-50">
                <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
                Log Trip
                <span class="ml-auto text-xs text-gray-400">L</span>
            </button>
        </div>

        <!-- Navigation -->
        <div class="flex-1 overflow-y-auto px-2 py-1 space-y-6">
            <!-- Main Links -->
            <div class="space-y-0.5">
                <div class="flex items-center gap-2 px-2 py-1 rounded-md bg-gray-200/50 text-gray-900 font-medium">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
                    Home
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
                    Inbox
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                    Messages
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
                    Docs
                </div>
                <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                    <svg class="w-4 h-4 text-gray-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
                    Calls
                </div>
            </div>

            <!-- Favorites -->
            <div>
                <div class="px-2 text-xs font-medium text-gray-400 mb-1">Favorites</div>
                <div class="space-y-0.5">
                    {#each favorites as fav}
                        <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                            {#if fav.icon === 'chart'}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 3v18h18"/><path d="M18 17V9"/><path d="M13 17V5"/><path d="M8 17v-3"/></svg>
                            {:else if fav.icon === 'trophy'}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M18 2H6v7a6 6 0 0 0 12 0V2z"/></svg>
                            {:else if fav.icon === 'star'}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
                            {:else}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/></svg>
                            {/if}
                            <span class="truncate">{fav.name}</span>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- Channels -->
            <div>
                <div class="px-2 text-xs font-medium text-gray-400 mb-1">Channels</div>
                <div class="space-y-0.5">
                    {#each channels as channel}
                        <div class="flex items-center gap-2 px-2 py-1 rounded-md text-gray-600 hover:bg-gray-100">
                            {#if channel.icon === 'trophy'}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M18 2H6v7a6 6 0 0 0 12 0V2z"/></svg>
                            {:else if channel.icon === 'shield'}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
                            {:else if channel.icon === 'star'}
                                <svg class="w-3.5 h-3.5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
                            {:else}
                                <span class="text-gray-400">#</span>
                            {/if}
                            <span class="truncate">{channel.name}</span>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col bg-white min-w-0">
        <!-- Header -->
        <div class="px-8 py-6 pb-2">
            <h2 class="text-2xl font-bold text-gray-900 mb-4">Home</h2>
            <div class="flex items-center justify-between border-b border-gray-100 pb-0">
                <div class="flex gap-6">
                    <button class="pb-2 border-b-2 border-black font-medium text-gray-900">For me</button>
                    <button class="pb-2 border-b-2 border-transparent font-medium text-gray-500 hover:text-gray-700">Created</button>
                    <button class="pb-2 border-b-2 border-transparent font-medium text-gray-500 hover:text-gray-700">All</button>
                </div>
                <button class="text-gray-400 hover:text-gray-600 mb-2">
                    <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="4" y1="21" x2="4" y2="14"/><line x1="4" y1="10" x2="4" y2="3"/><line x1="12" y1="21" x2="12" y2="12"/><line x1="12" y1="8" x2="12" y2="3"/><line x1="20" y1="21" x2="20" y2="16"/><line x1="20" y1="12" x2="20" y2="3"/><line x1="1" y1="14" x2="7" y2="14"/><line x1="9" y1="8" x2="15" y2="8"/><line x1="17" y1="16" x2="23" y2="16"/></svg>
                </button>
            </div>
        </div>

        <!-- Input -->
        <div class="px-8 py-4">
            <div class="flex gap-3 items-start">
                <div class="w-8 h-8 rounded-full bg-gray-200 flex-shrink-0"></div>
                <div class="flex-1 relative">
                    <input type="text" placeholder="Share your latest achievement..." class="w-full bg-transparent text-gray-900 placeholder-gray-400 focus:outline-none py-1.5" />
                </div>
                <button class="px-3 py-1.5 bg-gray-100 text-gray-400 rounded-md text-xs font-medium">Share</button>
            </div>
        </div>

        <!-- Feed -->
        <div class="flex-1 overflow-y-auto px-8 pb-8">
            <!-- Today -->
            <div class="mb-6">
                <h3 class="text-xs font-medium text-gray-400 mb-3">Today</h3>
                <div class="space-y-4">
                    {#each posts as post}
                        <div class="group flex gap-3 items-start">
                            <div class="w-8 h-8 rounded-md {post.iconBg} flex items-center justify-center text-white text-xs font-bold flex-shrink-0 mt-0.5 shadow-sm border border-black/5">
                                {#if post.icon === 'P'}
                                    <span class="font-serif italic">P</span>
                                {:else}
                                    {post.icon}
                                {/if}
                            </div>
                            <div class="flex-1 min-w-0">
                                <div class="flex items-baseline gap-2">
                                    <span class="font-medium text-gray-900 truncate">{post.title}</span>
                                </div>
                                <div class="flex items-center gap-1.5 text-gray-500 text-xs mt-0.5">
                                    <span class="font-medium text-gray-600">{post.author}:</span>
                                    <span class="truncate">{post.preview}</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 flex-shrink-0">
                                <span class="text-[10px] font-medium px-1.5 py-0.5 rounded bg-gray-50 {post.tagColor} border border-gray-100">{post.tag}</span>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- Yesterday -->
            <div>
                <h3 class="text-xs font-medium text-gray-400 mb-3">Yesterday</h3>
                <div class="space-y-4">
                    {#each yesterdayPosts as post}
                        <div class="group flex gap-3 items-start">
                             <div class="w-8 h-8 rounded-md {post.iconBg} flex items-center justify-center text-white text-xs font-bold flex-shrink-0 mt-0.5 shadow-sm border border-black/5">
                                {post.icon}
                            </div>
                            <div class="flex-1 min-w-0">
                                <div class="flex items-baseline gap-2">
                                    <span class="font-medium text-gray-900 truncate">{post.title}</span>
                                </div>
                                <div class="flex items-center gap-1.5 text-gray-500 text-xs mt-0.5">
                                    <span class="font-medium text-gray-600">{post.author}:</span>
                                    <span class="truncate">{post.preview}</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 flex-shrink-0">
                                <span class="text-[10px] font-medium px-1.5 py-0.5 rounded bg-gray-50 {post.tagColor} border border-gray-100">{post.tag}</span>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>

    <!-- Right Sidebar -->
    <div class="w-64 border-l border-gray-200 bg-gray-50 flex flex-col flex-shrink-0">
        <div class="p-3">
             <div class="relative">
                <svg class="absolute left-2.5 top-2 w-4 h-4 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
                <input type="text" placeholder="Search drivers..." class="w-full bg-white border border-gray-200 rounded-md pl-9 pr-3 py-1.5 text-sm placeholder-gray-400 focus:outline-none focus:border-gray-300" />
            </div>
        </div>

        <div class="flex-1 overflow-y-auto px-3 py-2">
            <div class="flex items-center gap-1.5 text-xs text-gray-400 font-medium mb-3">
                <svg class="w-3 h-3" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M18 2H6v7a6 6 0 0 0 12 0V2z"/></svg>
                Top Drivers
            </div>
            
            <div class="space-y-3">
                {#each team as member}
                    <div class="flex items-start gap-2">
                        <div class="relative">
                            <img src={member.img} alt={member.name} class="w-8 h-8 rounded-full bg-gray-200" />
                            {#if member.online}
                                <div class="absolute -bottom-0.5 -right-0.5 w-2.5 h-2.5 bg-green-500 border-2 border-gray-50 rounded-full"></div>
                            {/if}
                        </div>
                        <div class="flex-1 min-w-0">
                            <div class="flex items-center gap-1.5">
                                <span class="text-xs font-bold text-primary-600">{member.rank}</span>
                                <div class="text-sm font-medium text-gray-900 truncate">{member.name}</div>
                            </div>
                            {#if member.status}
                                <div class="text-xs text-gray-500 truncate flex items-center gap-1">
                                    {#if member.status === 'On the road'}
                                        <span>🚛</span>
                                    {:else if member.status === 'Loading'}
                                        <span>📦</span>
                                    {/if}
                                    {member.status}
                                </div>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>

             <div class="mt-6">
                <div class="flex items-center gap-1.5 text-xs text-gray-400 font-medium mb-3">
                    <svg class="w-3 h-3" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
                    Million Mile Club
                </div>
            </div>
        </div>
    </div>
</div>
