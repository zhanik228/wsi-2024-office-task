<template>
    <div class="sidebar">
        <div class="sidebar__header">
            <div class="avatar-container">
                <img width="120" height="120" :src="avatar" alt="avatar">
                <div class="avatar-description">
                    <h2 class="avatar-description__title">Mary</h2>
                    <p>Being at work 3h 46m</p>
                </div>
                <button class="end-button">End session</button>
            </div>
        </div>
        <div class="sidebar__body">
            <div v-for="body in sidebar_body" :key="body.title.name">
                <h2 :class="`sidebar__body-title ${body.title.bold ? 'bold' : ''}`">{{ body.title.name }} {{ `(${body.people.length}/${body.max_amount})` }}</h2>
                <div class="sidebar__body-names">
                        <p v-for="people in body.people" class="sidebar__body-name">{{ people }}</p>
                </div>
            </div>
        </div>
        <div class="sidebar__footer">
            <div class="chat">
                <h2 class="chat__title">The Office chat</h2>
                <div class="chat-body"></div>
                <h2 class="chat-message__title">Send Message: </h2>
                <input type="text" placeholder="...">
            </div>
        </div>
    </div>
</template>

<script>
import firstAvatar from '@/assets/avatars/avatar-01.svg'

export default {
    data() {
        return {
            avatar: firstAvatar,
            sidebar_body: [
                {
                    title: {
                        name: 'The office',
                        bold: true,
                    },
                    people: [
                        'Mary',
                        'Richard'
                    ],
                    max_amount: 4,
                },
                {
                    title: {
                        name: 'Desk',
                        bold: false,
                    },
                    people: [
                        'John',
                    ],
                    max_amount: 3
                }
            ]
        }
    }
}
</script>


<style scoped>
.bold {
    font-weight: 700;
}

.sidebar {
    display: flex;
    flex-direction: column;
    position: fixed;
    left: 0;
    background-color: rgb(152, 224, 224);
    height: 100%;
}

.sidebar__header {
    padding: 20px 10px;
    border-bottom: 1px solid #fff;
}

.avatar-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
}

.avatar-description__title {
    font-size: 24px;
}

.end-button {
    width: 100%;
    display: inline-block;
    padding: 5px 10px;
    background: rgb(212, 84, 105);
    border: none;
    border-radius: 4px;
    color: white;
    cursor: pointer;
}

.sidebar__body {
    margin-top: 15px;
    border-bottom: 1px solid #fff;
    flex-grow: 1;
}

.sidebar__body-title {
    margin-left: 20px;
    font-size: 18px;
}

.sidebar__body-names {
    margin-left: 35px;
}

.sidebar__footer {
    padding: 20px 10px;
}

.chat-body {
    background: #fff;
    width: 100%;
    height: 250px;
}

.chat {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
</style>